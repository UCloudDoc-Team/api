# 获取数据库日志 - ListUPgSQLLog

## 简介

获取数据库日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUPgSQLLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUPgSQLLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的日志开始的时间戳 |**Yes**|
| **EndTime** | int | 查询日志的结束时间戳 |**Yes**|
| **InstanceID** | string | 资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*LogSet*](#LogSet)] | 数据库日志信息列表 |**Yes**|

#### 数据模型


#### LogSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BeginTime** | int |  |No|
| **EndTime** | int |  |No|
| **Name** | string |  |No|
| **Size** | int |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUPgSQLLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FkcfKEtL
&BeginTime=4
&EndTime=3
&InstanceID=tcXRoalT
```

### 响应示例
    
```json
{
  "Action": "ListUPgSQLLogResponse",
  "DataSet": [
    {
      "BeginTime": 2,
      "EndTime": 5,
      "Name": "jQCYvUEY",
      "Size": 7
    }
  ],
  "Message": "MaECSfSr",
  "RetCode": 0
}
```





