# 获取实例容灾记录列表 - ListUDBInstanceFailoverRecord

## 简介

获取实例容灾记录列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDBInstanceFailoverRecord)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDBInstanceFailoverRecord`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DBId** | string | 实例id |**Yes**|
| **StartTime** | int | 开始时间 |**Yes**|
| **EndTime** | int | 结束时间 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Dataset** | array[[*FailoverRecord*](#FailoverRecord)] | 容灾记录列表 |**Yes**|

#### 数据模型


#### FailoverRecord

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SessionId** | string | 时间ID |No|
| **FailoverType** | int | 容灾类型 |No|
| **StartTime** | int | 开始时间 |No|
| **EndTime** | int | 结束时间 |No|
| **FailoverState** | string | 容灾状态 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDBInstanceFailoverRecord
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=YGOCONuQ
&DBId=ILWzMXLU
&StartTime=1
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "ListUDBInstanceFailoverRecordResponse",
  "Dataset": [
    {
      "EndTime": 4,
      "FailoverState": "KAZRYsrM",
      "FailoverType": 5,
      "SessionId": "MsctzLfl",
      "StartTime": 6
    }
  ],
  "Message": "gPrdRItY",
  "RetCode": 0
}
```





