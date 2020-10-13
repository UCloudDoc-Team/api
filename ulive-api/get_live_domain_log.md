# 获取直播加速域名日志 - GetLiveDomainLog

## 简介

获取直播加速域名日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetLiveDomainLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetLiveDomainLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DomainId.N** | string | 域名ID |No|
| **BeginTime** | int | 查询日志的起始时间，格式：时间戳。如果有EndTime，BeginTime必须赋值，如没有赋值，则返回缺少参数错误，如果没有EndTime，BeginTime也可以不复值，EndTime默认当前时间，BeginTime<br />默认前六天的当前时间（也就是返回前五天的数据）。 |No|
| **EndTime** | int | 查询日志的结束时间，格式：时间戳 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LogInfoSet** | array[[*DomainLogInfoSet*](#DomainLogInfoSet)] | 日志信息表。详见下面LogInfoSet |**Yes**|

#### 数据模型


#### DomainLogInfoSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 日志对应的域名ID |No|
| **LogInfo** | array[[*LogInfo*](#LogInfo)] | 具体日志信息表、详见下面LogInfo |No|

#### LogInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 生成日志的时间点，格式：时间戳 |No|
| **Value** | string | 具体获取日志连接的url |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetLiveDomainLog
```

### 响应示例
    
```json
{
  "Action": "GetLiveDomainLogResponse",
  "LogInfoSet": [
    {
      "DomainId": "ulive-acg4f1",
      "LogInfo": [
        {
          "Time": 1399305600,
          "Value": " http://XXXX.XX.X/XXXX"
        }
      ]
    }
  ],
  "RetCode": 0
}
```





