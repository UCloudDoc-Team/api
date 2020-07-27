# 签名算法

## 数据假设

在生成 API 请求中的签名（`Signature`） 时，需要提供账户中密钥，包括 `PublicKey` 和 `PrivateKey`，
密钥可以从 [UAPI 控制台](https://console.ucloud.cn/uapi/apikey) 获取。

本例中假设

```
PublicKey  = 'ucloudsomeone@example.com1296235120854146120'
PrivateKey = '46f09bb9fab4f12dfc160dae12273d5332b5debe'
```

?> 你可以使用上述的 `PublicKey` 和 `PrivateKey` 调试你的代码， 当得到跟后面一致的签名结果后（即表示你的代码是正确的），可再换为你自己的 `PublicKey` 和 `PrivateKey` 以及其他 API 请求。

本例中假设用户请求参数串如下:

```json
{
    "Action"     :  "DescribeUHostInstance",
    "Region"     :  "cn-bj2",
    "Limit"      :  10,
    "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120"
}
```

生成被签名串的 SHA1 签名，即是请求参数 `Signature` 的值。

按照上述算法，本例中，计算出的 `Signature` 为 **cba5cf5ec4d4233d206b1b54951e3787350a642f** 。

## 构造签名

### 1. 将请求参数按照名称进行升序排列

```json
{
    "Action"     :  "DescribeUHostInstance",
    "Limit"      :  10,
    "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120",
    "Region"     :  "cn-bj2"
}
```

### 2. 构造被签名参数串

被签名串的构造规则为: 被签名串 = 所有请求参数拼接(无需 HTTP 转义)。并在本签名串的结尾拼接 API 密钥的私钥（`PrivateKey`）。

```
ActionDescribeUHostInstanceLimit10PublicKeyucloudsomeone@example.com1296235120854146120Regioncn-bj246f09bb9fab4f12dfc160dae12273d5332b5debe
```

注意：

- 对于 bool 类型，应编码为 `true/false`
- 对于浮点数类型，如果小数部分为 0，应仅保留证书部分，如 `42.0` 应保留 `42`

### 3. 计算签名

使用 SHA1 编码被签名串，生成最终签名。

## 多语言 SDK

UCloud 提供了多种语言的 SDK，以供计算签名使用，可在程序中直接导入使用。

?> 如果使用 SDK 发起请求，SDK 会自动为请求签名，无需以下操作。

<!-- tabs:start -->

#### ** Python **

```python
from ucloud.core import auth

cred = auth.Credential(
    "ucloudsomeone@example.com1296235120854146120",
    "46f09bb9fab4f12dfc160dae12273d5332b5debe",
)
d = {'Action': 'DescribeUHostInstance', 'Region': 'cn-bj2', 'Limit': 10}
print(cred.verify_ac(d))
```

SDK 详细使用方法可参考 [官方文档](https://docs.ucloud.cn/opensdk-python/)

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
  d := "Action=DescribeUHostInstance&Limit=10&Region=cn-bj2"
  fmt.Println(cred.CreateSign(d))
}
```

SDK 详细使用方法可参考 [官方文档](https://docs.ucloud.cn/opensdk-go/)

<!-- tabs:end -->
