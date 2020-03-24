# 签名算法

在生成 API 请求中的签名(Signature) 时，需要提供账户中的 PublicKey 和 PrivateKey，本例中假设

```
PublicKey  = 'ucloudsomeone@example.com1296235120854146120'
PrivateKey = '46f09bb9fab4f12dfc160dae12273d5332b5debe'
```

?> 你可以使用上述的 PublicKey 和 PrivateKey 调试你的代码， 当得到跟后面一致的签名结果后(即表示你的代码是正确的)，可再换为你自己的 PublicKey 和 PrivateKey 以及其他 API 请求。

本例中假设用户请求参数串如下:

```json
{ 
    "Action"     :  "CreateUHostInstance",
    "Region"     :  "cn-bj2",
    "Zone"       :  "cn-bj2-04",
    "ImageId"    :  "f43736e1-65a5-4bea-ad2e-8a46e18883c2", 
    "CPU"        :  2,
    "Memory"     :  2048,
    "DiskSpace"  :  10,
    "LoginMode"  :  "Password",
    "Password"   :  "VUNsb3VkLmNu",
    "Name"       :  "Host01",
    "ChargeType" :  "Month",
    "Quantity"   :  1,
    "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120"
}
```

!> 上例中的 `Password` 值为 `UCloud.cn`，但是调用时需要用 base64 进行编码。编码方法：echo -n "UCloud.cn" |base64；输出结果为"VUNsb3VkLmNu"。

签名计算建议使用 UCloud SDK，只需配置 PublicKey/PrivateKey 即可为每一个请求自动计算签名，如需手动传递签名可以参考以下代码：

<!-- tabs:start -->

#### ** Python **

```python
from ucloud.core import auth

cred = auth.Credential(
    "ucloudsomeone@example.com1296235120854146120",
    "46f09bb9fab4f12dfc160dae12273d5332b5debe",
)
d = {'Action': 'CreateUHostInstance', 'Region': 'cn-bj2', 'Zone': 'cn-bj2-04', 'ImageId': 'f43736e1-65a5-4bea-ad2e-8a46e18883c2', 'CPU': 2, 'Memory': 2048, 'DiskSpace': 10, 'LoginMode': 'Password', 'Password': 'VUNsb3VkLmNu', 'Name': 'Host01', 'ChargeType': 'Month', 'Quantity': 1, 'PublicKey': 'ucloudsomeone@example.com1296235120854146120'}
print(cred.verify_ac(d))
```

> 详情可参考开源 [示例代码](https://github.com/ucloud/ucloud-sdk-python3/blob/master/tests/test_unit/test_core/test_auth.py#L4)。

#### ** Go **

```go
package main

import (
  "fmt"
  "github.com/ucloud/ucloud-sdk-go/ucloud/auth"
)

func main() {
  cred := &auth.Credential{
    PublicKey:  "ucloudsomeone@example.com1296235120854146120",
    PrivateKey: "46f09bb9fab4f12dfc160dae12273d5332b5debe",
  }
  d := "Action=CreateUHostInstance&CPU=2&ChargeType=Month&DiskSpace=10&ImageId=f43736e1-65a5-4bea-ad2e-8a46e18883c2&LoginMode=Password&Memory=2048&Name=Host01&Password=VUNsb3VkLmNu&PublicKey=ucloudsomeone%40example.com1296235120854146120&Quantity=1&Region=cn-bj2&Zone=cn-bj2-04"
  fmt.Println(cred.CreateSign(d))
}
```

<!-- tabs:end -->

生成被签名串的 SHA1 签名，即是请求参数 `Signature` 的值。

按照上述算法，本例中，计算出的 Signature 为  **4f9ef5df2abab2c6fccd1e9515cb7e2df8c6bb65** 。

## 构造 HTTP 请求详细流程

### 1. 将请求参数按照名进行升序排列

```json
{ 
    "Action"     :  "CreateUHostInstance",
    "CPU"        :  2,
    "ChargeType" :  "Month",
    "DiskSpace"  :  10,
    "ImageId"    :  "f43736e1-65a5-4bea-ad2e-8a46e18883c2", 
    "LoginMode"  :  "Password",
    "Memory"     :  2048,
    "Name"       :  "Host01",
    "Password"   :  "VUNsb3VkLmNu",
    "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120",
    "Quantity"   :  1,
    "Region"     :  "cn-bj2",
    "Zone"       :  "cn-bj2-04"
}
```

### 2. 构造被签名参数串

被签名串的构造规则为: 被签名串 = 所有请求参数拼接(无需 HTTP 转义)。并在本签名串的结尾拼接 API 密钥的私钥（PrivateKey）。

```
ActionCreateUHostInstanceCPU2ChargeTypeMonthDiskSpace10ImageIdf43736e1-65a5-4bea-ad2e-8a46e18883c2LoginModePasswordMemory2048NameHost01PasswordVUNsb3VkLmNuPublicKeyucloudsomeone@example.com1296235120854146120Quantity1Regioncn-bj2Zonecn-bj2-0446f09bb9fab4f12dfc160dae12273d5332b5debe
```

### 3. 计算签名

对于 OpenSDK 尚未支持的编程语言，可以参考以下签名算法的实现自行签名。

<!-- tabs:start -->

#### ** Python **

?> 完整示例请参考 [Python SDK Auth](https://github.com/ucloud/ucloud-sdk-python3/blob/master/ucloud/core/auth/_cfg.py#L41) 模块，且建议直接使用 SDK 自动对请求签名，**对于 SDK 暂不支持的接口，SDK 也提供了[泛化调用方式
](https://docs.ucloud.cn/opensdk-python/generic) 支持自动计算签名**，以下是简化过的示例：

```python
from collections import OrderedDict

def verify_ac(private_key: str, params: dict) -> str:
    params = OrderedDict(sorted(params.items(), key=lambda item: item[0]))

    simplified = ""
    for key, value in params.items():
        simplified += str(key) + encode_value(value)
    simplified += private_key

    hash_new = hashlib.sha1()
    hash_new.update(simplified.encode("utf-8"))
    hash_value = hash_new.hexdigest()
    return hash_value

def encode_value(v):
    # bool only accept lower case
    if isinstance(v, bool):
        return "true" if v else "false"

    # api gateway will try to decode float as int in lua syntax
    if isinstance(v, float):
        return str(int(v)) if v % 1 == 0 else str(v)
    return str(v)
```

#### ** PHP **

!> PHP 中签名计算不支持 Boolean 类型，该类型元素请传递字符串 "true" 或 "false"

```php
<?php
function verify_ac($private_key, $params) {
  ksort($params);

  $params_data = "";

  foreach($params as $key => $value) {
    $params_data .= $key;
    $params_data .= $value;
  }

  $params_data .= $private_key;
  return sha1($params_data); 
}

$cred = [
  "PublicKey" => "ucloudsomeone@example.com1296235120854146120",
  "PrivateKey" => "46f09bb9fab4f12dfc160dae12273d5332b5debe",
];

$params = [ 
  "Action"     =>  "CreateUHostInstance",
  "Region"     =>  "cn-bj2",
  "Zone"       =>  "cn-bj2-04",
  "ImageId"    =>  "f43736e1-65a5-4bea-ad2e-8a46e18883c2", 
  "CPU"        =>  2,
  "Memory"     =>  2048,
  "DiskSpace"  =>  10,
  "LoginMode"  =>  "Password",
  "Password"   =>  "VUNsb3VkLmNu",
  "Name"       =>  "Host01",
  "ChargeType" =>  "Month",
  "Quantity"   =>  1,
  "PublicKey"  =>  $cred["PublicKey"],
];

print(verify_ac($cred["PrivateKey"], $params));
?>
```

<!-- tabs:end -->

### 4.使用签名组合HTTP请求

#### 4.1 Json方式

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{ 
​    "Action"     :  "CreateUHostInstance",
​    "ChargeType" :  "Month",
​    "CPU"        :  2,
​    "DiskSpace"  :  10,
​    "ImageId"    :  "f43736e1-65a5-4bea-ad2e-8a46e18883c2", 
​    "LoginMode"  :  "Password",
​    "Memory"     :  2048,
​    "Name"       :  "Host01",
​    "Password"   :  "VUNsb3VkLmNu",
​    "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120",
​    "Quantity"   :  1,
​    "Region"     :  "cn-bj2",
​    "Zone"       :  "cn-bj2-04",
    "Signature"  :  "4f9ef5df2abab2c6fccd1e9515cb7e2df8c6bb65"
}'
```

#### 4.2 拼接参数方式

对排序后的请求参数进行URL编码，URL 编码的规则遵循 [RFC3986](https://tools.ietf.org/html/rfc3986)，概括如下：

* 字符 A-Z、a-z、0-9 不编码；
* 字符“-”、“_”、“.”、“~”不编码；
* 其它字符编码成 %XY 的格式，其中 XY 是字符对应 ASCII 码的 16 进制表示。比如：英文的双引号（”）对应的编码为 %22；
* 对于扩展的 UTF-8 字符，编码成 %XY%ZA… 的格式；
* 英文空格（ ）要编码成 %20，而不是加号（+）。
* "PublicKey" 无需编码

构造HTTP请求，参数名和参数值之间用 "=" 连接，参数和参数之间用"&"号连接，构造的URL请求为:

```
http(s)://api.ucloud.cn/?Action=CreateUHostInstance
&CPU=2
&ChargeType=Month
&DiskSpace=10
&ImageId=f43736e1-65a5-4bea-ad2e-8a46e18883c2
&LoginMode=Password
&Memory=2048
&Name=Host01
&Password=VUNsb3VkLmNu
&PublicKey=ucloudsomeone%40example.com1296235120854146120
&Quantity=1
&Region=cn-bj2
&Zone=cn-bj2-04
```

将签名参数附在原有请求串的最后面。最终的 HTTP 请求串为(为了查看方便，我们人为地将参数之间用回车分隔开),完整的请求 URL 如下：(为了方便，我们人为地将参数之间用回车分隔开)

```
http(s)://api.ucloud.cn/?Action=CreateUHostInstance
&CPU=2
&ChargeType=Month
&DiskSpace=10
&ImageId=f43736e1-65a5-4bea-ad2e-8a46e18883c2
&LoginMode=Password
&Memory=2048
&Name=Host01
&Password=VUNsb3VkLmNu
&PublicKey=ucloudsomeone%40example.com1296235120854146120
&Quantity=1
&Region=cn-bj2
&Zone=cn-bj2-04
&Signature=4f9ef5df2abab2c6fccd1e9515cb7e2df8c6bb65
```
