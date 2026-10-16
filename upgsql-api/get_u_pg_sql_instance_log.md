# 查询日志 - GetUPgSQLInstanceLog

## 简介

可以查询DB的错误日志和满查询日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUPgSQLInstanceLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPgSQLInstanceLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **LogType** | string | 日志类型 |**Yes**|
| **CompanyID** | int | 公司ID |**Yes**|
| **AccountID** | int | 账户ID |**Yes**|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **InstanceID** | string | 实例资源ID |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间<br />实时查询的时候不需要传 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Log** | string | 返回的日志信息 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPgSQLInstanceLog
&Region=cn-zj
&ProjectId=hjoEHCAh
&ZoneID=666003001
&DBId=hZkoNEiZ
&LogType=sDVQeSdg
&CompanyID=6
&AccountID=6
&BeginTime=9
&EndTime=3
```

### 响应示例
    
```json
{
  "Action": "GetUPgSQLInstanceLogResponse",
  "Log": "qxfLrSZN",
  "RetCode": 0
}
```





