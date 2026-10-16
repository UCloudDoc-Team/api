# 获取团队操作日志列表 - ListCompShareTeamOperateLog

## 简介

获取团队操作日志列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCompShareTeamOperateLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |**Yes**|
| **TeamId** | int | 团队ID |**Yes**|
| **Limit** | int | 返回数据长度，默认为25，最大100 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **OperateType.N** | string | 操作类型，详细参考返回值 |No|
| **Status.N** | string | 操作状态，详细参考返回值 |No|
| **OrderByASC** | boolean | 排序方式：true表示按创建时间升序，false表示降序（默认） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Logs** | array[[*CompShareTeamOperateLogInfo*](#CompShareTeamOperateLogInfo)] | 团队操作日志列表 |**Yes**|
| **Total** | int | 总条目数 |**Yes**|
| **OperateTypeList** | array[string] | 操作类型枚举列表 |No|
| **StatusList** | array[string] | 状态枚举列表 |No|

#### 数据模型


#### CompShareTeamOperateLogInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Content** | string | 操作内容 |No|
| **OperateType** | string | 操作类型 |No|
| **CreateTime** | int | 操作日志的创建时间 |No|
| **Status** | string | 操作状态 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCompShareTeamOperateLog
&BeginTime=2
&EndTime=4
&TeamId=1
&Limit=7
&Offset=8
&OperateType=CreateTeam
&Status=Success
&OrderByASC=true
```

### 响应示例
    
```json
{
  "Action": "ListCompShareTeamOperateLogResponse",
  "Logs": [
    {
      "Content": "fDkxMvZR",
      "CreateTime": 4,
      "OperateType": "创建团队、更新团队、分配金额、提取金额、发送邀请、取消邀请、接受邀请、拒绝邀请",
      "Status": "成功、失败"
    }
  ],
  "OperateTypeList": [
    "fbdPLIJw"
  ],
  "RetCode": 0,
  "StatusList": [
    "SPiVRIkG"
  ],
  "Total": 8
}
```





