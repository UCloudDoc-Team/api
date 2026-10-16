# 查询日志主题采集配置列表 - ListULogServiceCollectConf

## 简介

查询日志主题采集配置列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListULogServiceCollectConf)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListULogServiceCollectConf`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TopicId** | int | 日志主题ID |**Yes**|
| **CollectConfId** | int | 采集配置ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CollectConfs** | [*CollectConf*](#CollectConf) | 日志采集配置列表 |**Yes**|

#### 数据模型


#### CollectConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TopicId** | int | 日志主题ID |**Yes**|
| **State** | int | State |**Yes**|
| **MachineGroups** | array[[*MachineGroup*](#MachineGroup)] | 机器组ID，是一个数组 |**Yes**|
| **Id** | int | Id |No|
| **Name** | string | 日志采集配置名称 |No|
| **LogType** | string | 日志解析类型，决定了如何结构化日志。可选值: json:json 格式，delimiter:分隔符，full_regex:完全正则，multi_line_full_regex:多行完全正则，multi_line_delimiter: 多行分隔符正则，minimal_list:单行全文日志,multi_line:多行全文日志 |No|
| **CollectPolicy** | string | 采集策略。可选值: full (全量采集存量日志), increment (从当前时间点增量采集)。默认为 full。 |No|
| **Encode** | string | 日志原文的编码格式。可选值: utf-8, gbk。默认为 utf-8。 |No|
| **Keys** | string | 索引字段key，是一个数组 |No|
| **Delimiter** | string | 当 LogType 为delimiter 或multi_line_delimiter时可选，支持多字符分隔，需要转换成Base64 |No|
| **MatchRule** | string | 行首正则表达式。当 logType 为多行模式 (如 multi_line 或 multi_line_full_regex或multi_line_delimiter) 时，用于标识一条新日志的开始。需要转换成Base64 |No|
| **ExtractRule** | string | 日志提取正则表达式。当 logType 为正则模式 (如 full_regex,multi_line_full_regex) 时，用于从日志中提取字段。需要转换成Base64 |No|
| **UnMatchKey** | string | 如果 UnMatchUpload 为 true，无法解析的日志原文将被存放在此字段指定的 Key 下。默认为 LogParseFailure。 |No|
| **FilePaths** | array[[*FilePath*](#FilePath)] | FilePaths |No|
| **CreateTime** | int | CreateTime |No|
| **UpdateTime** | int | updateTime |No|

#### MachineGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 机器组ID |No|
| **Name** | string | 机器组名称 |No|
| **Type** | string | 采集器识别类型：LABEL：机器标识，IP：IP类型 |No|
| **CreateTime** | int | 创建时间 |No|
| **UpdateTime** | int | 修改时间 |No|

#### FilePath

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Path** | string | 路径 |No|
| **File** | string | 文件名 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListULogServiceCollectConf
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DFEtGDxk
&InstanceId=wGhxQlXm
&TopicId=8
&CollectConfId=4
```

### 响应示例
    
```json
{
  "Action": "ListULogServiceCollectConfResponse",
  "Data": [
    {
      "CreateTime": 8,
      "LogCollectConf": "ibmLfliC",
      "LogCollectMode": "HiJbOcWY",
      "LogTopicId": 8,
      "UpdateTime": 1
    }
  ],
  "MachineGroups": [
    {
      "CreateTime": 5,
      "Id": "ABLDyOLy",
      "IsReserved": 7,
      "Name": "ANVVqZhZ",
      "Type": 6,
      "UpdateTime": 8
    }
  ],
  "Message": "JtUYImzS",
  "RetCode": 0
}
```





