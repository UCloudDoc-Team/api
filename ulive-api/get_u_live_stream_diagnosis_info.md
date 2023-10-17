# 获取直播流诊断信息 - GetULiveStreamDiagnosisInfo

## 简介

获取直播流诊断信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveStreamDiagnosisInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveStreamDiagnosisInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | string | UNIX时间戳，单位：ms |**Yes**|
| **EndTime** | string | UNIX时间戳，单位：ms |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **App** | string | 发布点 |**Yes**|
| **StreamName** | string | 流名 |**Yes**|
| **StreamSuffix** | string | 流后缀 |**Yes**|
| **Phase** | int | 阶段<br />- 0：推流/源流<br />- 1：转码流<br />- 2：拉流 |**Yes**|
| **IntervalType** | string | 数据粒度<br />- aggr: 1min 聚合数据，取均值 （默认）<br />- detailed：明细数据 (未聚合的数据) 比如5秒/10秒 |No|
| **RequestType** | string | 请求类型<br />- all：获诊断结果并返回指标数据 （默认）<br />- metrics：仅查询指标，不做诊断 |No|
| **PullStreamSessionID** | string | 拉流SessionID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResponseMetadata** | [*ResponseMetadata*](#ResponseMetadata) | 元信息 |No|
| **Result** | [*ResultData*](#ResultData) | 结果 |No|

#### 数据模型


#### ResponseMetadata

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RequestId** | string | 请求ID |No|
| **Error** | [*ErrorMessage*](#ErrorMessage) | 接口错误信息, 请求成功时为空 |No|

#### ResultData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 开始时间 |No|
| **EndTime** | int | 结束时间 |No|
| **Domain** | string | 域名 |No|
| **App** | string | 发布点 |No|
| **StreamName** | string | 流名 |No|
| **StreamSuffix** | string | 流后缀 |No|
| **Phase** | int | 阶段 |No|
| **PullStreamSessionID** | string | 拉流sessionID (入参) |No|
| **NodeMetrics** | array[[*NodeMetrics*](#NodeMetrics)] | 指标 |No|
| **DiagnoseResult** | array[[*DiagnoseInfo*](#DiagnoseInfo)] | 诊断结果 |No|

#### NodeMetrics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PushStreamSessionID** | string | 推流SessionID，CDN对一个连接的唯一标识id即可 |No|
| **CdnNodeIP** | string | cdn 节点IP |No|
| **CdnNodeProvince** | string | cdn 节点省份 |No|
| **CdnNodeCity** | string | cdn 节点城市 |No|
| **CdnNodeName** | string | cdn 节点名称 |No|
| **Metrics** | array[[*Metrics*](#Metrics)] | 节点指标 |No|

#### DiagnoseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AbnormalEvent** | string | 异常事件 key，见异常事件列表 |No|
| **EventTime** | int | 异常时间点，UNIX时间戳，单位：ms |No|
| **Duration** | int | 持续时间，ms |No|
| **Message** | string | 异常信息 |No|
| **Reason** | string | 异常原因 |No|

#### Metrics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MetricName** | string | 指标名(英文字段名) |No|
| **MetricsItems** | array[[*MetricsItem*](#MetricsItem)] | 指标明细数据 |No|

#### MetricsItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ts** | int | 时间戳 |No|
| **Value** | float | 指标值 |No|

#### ErrorMessage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Code** | string | 错误code |No|
| **Message** | string | 错误描述 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveStreamDiagnosisInfo
&ProjectId=RBwguEkQ
&StartTime=forxUPtv
&EndTime=NTFSZTTJ
&Domain=zaMmmqEj
&App=pjsEJuHK
&StreamName=MGodyiMt
&StreamSuffix=PeUKKVda
&Phase=3
&IntervalType=FXGKhPMo
&RequestType=gXsLOcmd
&PullStreamSessionID=qNrRGtSC
```

### 响应示例
    
```json
{
  "Action": "GetULiveStreamDiagnosisInfoResponse",
  "ResponseMetadata": {},
  "Result": {},
  "RetCode": 0
}
```





