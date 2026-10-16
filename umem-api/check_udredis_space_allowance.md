# 检查高性能UMem剩余资源 - CheckUDredisSpaceAllowance

## 简介

检查高性能UMem剩余资源，以及分片扩容前的资源预检查






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CheckUDredisSpaceAllowance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CheckUDredisSpaceAllowance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Size** | int | 创建实例的容量大小,，扩容时的分片目标容量大小 |**Yes**|
| **Count** | string | 创建实例的数量，[1-10] |**Yes**|
| **GroupId** | string | 资源ID，扩缩容时的必传参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Count** | int | 创建实例资源时，表示可创建的数量；扩容资源时，返回1表示可以扩容，0表示可用区资源不足不能扩容 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CheckUDredisSpaceAllowance
&Region=baQYMUCr
&Zone=KsoovIkN
&Size=nSRPldjY
&Count=fFoecQur
&GroupId=mJadWYEV
```

### 响应示例
    
```json
{
  "Action": "CheckUDredisSpaceAllowanceResponse",
  "Count": 7,
  "NeedMigrate": "zgysRHAz",
  "RetCode": 0
}
```





