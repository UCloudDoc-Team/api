# 查询ULogService日志 - QueryULogServiceLog

## 简介

查询ULogService日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryULogServiceLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryULogServiceLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **QueryCriteria** | string | 查询条件，使用Base64编码。目前只支持查询索引，多个索引查询使用AND。比如:index1:http AND index2:http2 |**Yes**|
| **SortOrder** | string | 日志时间排序;可选值ASC\|DESC |**Yes**|
| **TopicId** | string | 主题ID |**Yes**|
| **StartTime** | int | 起始日志时间，秒级时间戳 |No|
| **EndTime** | int | 终止日志时间，秒级时间戳 |No|
| **Size** | int | 一次返回条数，默认20 |No|
| **ScrollId** | string | Deprecated. 滚动加载参数ScrollId |No|
| **LastId** | string | 滚动加载参数,上一页最后一条数据的ID |No|
| **LastTimestamp** | string | 滚动加载参数,上一页最后一条数据的timestamp |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*LogQueryResult*](#LogQueryResult) | 请求结果 |No|

#### 数据模型


#### LogQueryResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TopicId** | string | 所属日志ID |**Yes**|
| **TopicName** | string | 所属日志名称 |**Yes**|
| **IsOver** | boolean | 检索结果是否到底 |**Yes**|
| **Contents** | [*LogContent*](#LogContent) | 日志内容 |**Yes**|
| **ScrollId** | string | 滚动检索Id Deprecated |No|
| **LastId** | string | 滚动检索,当前页最后一条数据ID |No|
| **LastTimestamp** | string | 滚动检索,当前页最后一条数据Timestamp |No|

#### LogContent

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LogId** | string | 日志标识ID |**Yes**|
| **Timestamp** | int | 日志时间 |**Yes**|
| **LogJson** | string | JSON格式的日志内容 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryULogServiceLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=SgbifEuK
&InstanceId=TJSxOQgh
&LogTopicId=1
&QueryCriteria=VgbeimsE
&SortOrder=dJNfFKkb
&Limit=5
&Context=pPwqwavg
&StartTime=9
&EndTime=5
&StartTime=7
&EndTime=2
&LastId=PnnScnrE
&LastTimestamp=kiLBtvYo
```

### 响应示例
    
```json
{
  "Action": "QueryULogServiceLogResponse",
  "Data": {},
  "RetCode": 0
}
```





