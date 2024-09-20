# 获取用户操作日志 - GetUserOperationEvents

## 简介

获取用户操作日志

?> 通过该 API 目前只能查询最近365天的日志




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUserOperationEvents)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUserOperationEvents`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 开始时间（UNIX时间戳） |No|
| **EndTime** | int | 结束时间（UNIX时间戳） |No|
| **MaxResults** | int | 一次查询的最大记录数 |No|
| **NextToken** | string | 用于于请求下一页查询结果。请求参数必须与上次请求一致 |No|
| **ResourceID** | string | 资源 ID，用于搜索某个资源关联的操作日志 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NextToken** | string | 用于于请求下一页查询结果。请求参数必须与上次请求一致 |No|
| **Events** | array[[*UserOperationEvent*](#UserOperationEvent)] | 操作事件列表 |No|

#### 数据模型


#### UserOperationEvent

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **Api** | string | 操作的 API |No|
| **IsSuccess** | boolean | 是否成功 |No|
| **OperateTime** | int | 操作时间 |No|
| **UserName** | string | 用户名 |No|
| **UserEmail** | string | 用户邮箱 |No|
| **RelatedResource** | array[[*RelatedResource*](#RelatedResource)] | 操作事件关联的资源 |No|

#### RelatedResource

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源 ID |No|
| **ResourceName** | string | 资源名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUserOperationEvents
&ProjectId=DybfOwNo
&BeginTime=2
&EndTime=4
&MaxResults=7
&NextToken=nLgQPnKo
&ResourceID=CfrwODDl
```

### 响应示例
    
```json
{
  "Action": "GetUserOperationEventsResponse",
  "Events": [
    {
      "Api": "kNELMpfb",
      "IsSuccess": true,
      "OperateTime": 2,
      "Region": "sLtsxECu",
      "RelatedResource": [
        {
          "ResourceId": "HcWkaBoa",
          "ResourceName": "yVfCJcnu"
        }
      ],
      "UserEmail": "oZHZSIVq",
      "UserName": "MMmTomWP"
    }
  ],
  "NextToken": "SpWAGVWQ",
  "RetCode": 0
}
```





