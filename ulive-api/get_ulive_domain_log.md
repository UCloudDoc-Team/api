# 获取直播域名下的日志 - GetUliveDomainLog

## 简介

获取直播域名日志信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUliveDomainLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUliveDomainLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 起始时间，需使用时间戳 |**Yes**|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |**Yes**|
| **Domain.N** | string | 域名列表，n正整数，从0递增 |**Yes**|
| **Type** | string | 时间粒度 day=按天日志  hour=小时日志  fivemin=5分钟日志，默认day |No|
| **Area** | string | 日志区域：cn=国内  abroad=国外，默认cn |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LogInfoSet** | array[[*ULiveDomainLogSetItem*](#ULiveDomainLogSetItem)] | 日志信息 |**Yes**|

#### 数据模型


#### ULiveDomainLogSetItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LogInfoList** | array[[*ULiveDomainLogItem*](#ULiveDomainLogItem)] |  |**Yes**|
| **Domain** | string |  |**Yes**|

#### ULiveDomainLogItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 日志时间 |No|
| **LogUrlList** | array[string] | 日志url列表 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUliveDomainLog
&ProjectId=QfniyEtt
&BeginTime=2
&EndTime=9
&Domain.n=AVbxAwxv
&Type=JbptTWXJ
&Area=bURWGFPu
```

### 响应示例
    
```json
{
  "Action": "GetUliveDomainLogResponse",
  "LogInfoSet": [
    {
      "Domain": "mvlrPgRe",
      "LogInfoList": [
        {
          "LogUrlList": [
            "TmBSuDHw"
          ],
          "Time": 7
        }
      ]
    }
  ],
  "RetCode": 0
}
```





