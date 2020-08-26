# 启用读写分离功能 - EnableUDBRWSplitting

## 简介

开启DB的读写分离功能






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=EnableUDBRWSplitting)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `EnableUDBRWSplitting`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **MasterDBId** | string | DB实例ID（主库） |**Yes**|
| **BackupZone** | string | 备份的可用区。用于创建跨可用区读写分离的一个节点，跨机房的读写分离必须有这个参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MasterDBId** | string | DB实例ID（主库） |No|
| **RWIP** | string | 读写分离访问IP |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=EnableUDBRWSplitting
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=DMfqCmki
```

### 响应示例
    
```json
{
  "Action": "EnableUDBRWSplittingResponse",
  "MasterDBId": "WGLtSDkR",
  "RWIP": "VaaMPTNO",
  "RetCode": 0
}
```





