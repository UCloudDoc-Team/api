# 普通升级为方舟机型 - UpgradeToArkUHostInstance

## 简介

普通升级为方舟机型

?> 升级注意事项：仅支持普通型+本地盘的组合，需要关机进行，且整个升级过程较慢，每100G约需要等待30分钟。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpgradeToArkUHostInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeToArkUHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **UHostIds.N** | string | UHost主机的资源ID，例如UHostIds.0代表希望升级的主机1，UHostIds.1代表主机2。 |**Yes**|
| **CouponId** | string | 代金券ID 请参考DescribeCoupon接口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostSet** | array[string] | UHost主机的资源ID数组 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpgradeToArkUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostIds.0=uhost-xxx
```

### 响应示例
    
```json
{
  "Action": "UpgradeToArkUHostInstanceResponse",
  "RetCode": 0,
  "UHostSet": [
    "uhost-xxx"
  ]
}
```





