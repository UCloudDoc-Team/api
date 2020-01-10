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

## 构造HTTP请求详细流程

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

签名计算建议使用 UCloud SDK，只需配置 PublicKey/PrivateKey 即可为每一个请求自动计算签名。

各语言签名计算模块请参考以下 Github 源码。

| 语言   | 完整源码地址                                                 | 简短示例                       |
| ------ | ------------------------------------------------------------ | ------------------------------ |
| Python | [Github](https://github.com/ucloud/ucloud-sdk-python3/blob/master/ucloud/core/auth/_cfg.py#L41) | [详见此文档](#Python 简短示例) |
| Go     | [Github](https://github.com/ucloud/ucloud-sdk-go/blob/master/ucloud/auth/credential.go#L16) | [详见此文档](#Go 简短示例)     |
| Java   | [Github](https://github.com/ucloud/ucloud-sdk-java/blob/master/ucloud-sdk-java-common/src/main/java/cn/ucloud/common/util/Signature.java) | -                              |
| PHP    | -                                                            | [详见此文档](#PHP 简短示例)    |

生成被签名串的 SHA1 签名，即是请求参数 `Signature` 的值。

按照上述算法，本例中，计算出的 Signature 为 **4f9ef5df2abab2c6fccd1e9515cb7e2df8c6bb65** 。

#### Python 简短示例

完整示例请参考 [Python SDK Auth]() 模块，且建议使用 SDK 自动对请求签名，以下是简化过的示例：

```python
import hashlib
import urlparse
import urllib

def verify_ac(private_key, params):
​   items=params.items()
​   items.sort()

    params_data = "";
    for key, value in items:
        params_data = params_data + str(key) + str(value)
    params_data = params_data + private_key

    sign = hashlib.sha1()
    sign.update(params_data)
    signature = sign.hexdigest()
    return signature
```

#### Go 简短示例

#### PHP 简短示例

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

### 4.使用签名组合HTTP请求

#### 4.1 Json方式

```
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

对排序后的请求参数进行URL编码，URL 编码的规则如下：
* 字符 A-Z、a-z、0-9不编码；
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
