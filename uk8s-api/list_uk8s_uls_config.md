# 查询 UK8s 的 ULS 日志采集配置 - ListUK8SULSConfig

## 简介

查询 UK8S 的 ULSConfig









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUK8SULSConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TopicID** | string | 日志服务中用于接收日志的目标 TopicId。 |**Yes**|
| **ClusterId** | string | 集群 Id，如果不填，返回该账号该地域所有集群的 ULSConfig |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LogConfig** | array[[*ULSLogConfig*](#ULSLogConfig)] | 日志服务配置,见 ClusterLogConfig |**Yes**|

#### 数据模型


#### ULSLogConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClusterId** | string | uk8s集群id |**Yes**|
| **MachineGroup** | string | 机器组 |**Yes**|
| **ExtractRule** | [*ULSExtractRule*](#ULSExtractRule) | 定义日志的提取、解析和格式化规则。见 ULSExtractRule |No|
| **InputDetail** | [*ULSInputDetail*](#ULSInputDetail) | 定义日志的输入来源（例如容器文件）。见 ULSInputDetail |No|
| **MatchRule** | [*ULSMatchRule*](#ULSMatchRule) | 定义此采集规则要匹配的目标 Pod 或工作负载。<br />见 ULSMatchRule |No|
| **TopicID** | string | 日志服务中用于接收日志的目标 Topic ID。 |No|
| **Name** | string | 采集配置规则名称 |No|

#### ULSExtractRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CollectPolicy** | string | 采集策略。可选值: full (全量采集存量日志), increment (从当前时间点增量采集)。默认为 full。 |No|
| **Encode** | string | 日志原文的编码格式。可选值: utf-8, gbk。默认为 utf-8。 |No|
| **LogType** | string | 日志解析类型，决定了如何结构化日志。 |No|
| **Delimiter** | string | 当 LogType 为delimiter_log 时可选，可选字段 ' ',' ','\|',';',',' |No|
| **BeginningRegex** | string | 行首正则表达式。当 logType 为多行模式 (如 multiline_log 或 multiline_fullregex_log) 时，用于标识一条新日志的开始。 |No|
| **LogRegex** | string | 日志提取正则表达式。当 logType 为正则模式 (如 fullregex_log 或 multiline_fullregex_log) 时，用于从日志中提取字段。 |No|
| **TimeKey** | string | 指定时间字段。 |No|
| **TimeFormat** | string | timeKey 对应的时间格式。如： %Y-%m-%d %H:%M:%S |No|
| **UnMatchUpload** | string | 是否上传解析失败的日志。true 表示上传，false 表示丢弃。默认为 false。 |No|
| **UnMatchKey** | string | 如果 unMatchUpload 为 true，无法解析的日志原文将被存放在此字段指定的 Key 下。默认为 LogParseFailure。 |No|

#### ULSInputDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FilePaths** | array[[*ULSFilePaths*](#ULSFilePaths)] | 采集路径，数组。 |No|
| **Type** | string | 日志输入类型。当前主要支持 container_file，表示采集容器标准输出或文件。 |No|
| **InputMetadata** | [*ULSInputMetadata*](#ULSInputMetadata) | 定义哪些容器相关的元数据需要附加到日志中。 |No|

#### ULSMatchRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ContainerOperator** | string | 容器名称匹配操作符。支持：in(包含)，notin(不包含) |**Yes**|
| **Container** | string | 要匹配的容器名称，*表示所有容器，用逗号分隔 |**Yes**|
| **Workloads** | array[[*ULSWorkloadMatch*](#ULSWorkloadMatch)] | 按工作负载进行匹配。 |No|
| **PodLabels** | [*ULSPodLabelsMatch*](#ULSPodLabelsMatch) | 按 Pod 的标签进行匹配，提供更灵活的选择。 |No|

#### ULSWorkloadMatch

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Namespace** | string | 工作负载所在的命名空间。 |No|
| **Type** | string | 工作负载的类型，例如 deployment, statefulset, daemonset,cronjob,job。 |No|
| **Name** | string | 工作负载的名称。 |No|

#### ULSPodLabelsMatch

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NamespaceOperator** | string | 命名空间名称的匹配操作符。可选值: in, notin。 |No|
| **Namespace** | string | 要匹配的命名空间。namespaceOperator 存在时必需。 |No|
| **Labels** | array[[*ULSLabels*](#ULSLabels)] | 一个标签选择器数组，用于定义匹配的标签条件。 |No|

#### ULSLabels

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 要匹配的标签的 Key。 |No|
| **ValueOperator** | string | 标签值的匹配操作符。可选值: in, notin。 |No|
| **Value** | string | 要匹配的标签的值。 |No|

#### ULSFilePaths

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Path** | string | 定义采集路径 |No|
| **File** | string | 采集文件 |No|

#### ULSInputMetadata

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Container** | string | 指定具体要采集元数据的容器名。如果留空，则不采集容器的元数据，可选字段：container_name,namespace,pod_name,pod_ip,pod_uid,container_id,image_name。Pod Label 元数据通过指定 InputDetail.Metadata.Labels 字段。 |No|
| **Labels** | string | 定义要采集哪些 Pod 的标签 (Labels)。可选值：*：采集所有标签。app,version：仅采集 app 和 version 这两个标签。""（空字符串）：不采集任何标签。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUK8SULSConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FUgCRzMm
&TopicId=NCbAXMbi
&ClusterId=nkxapMln
```

### 响应示例
    
```json
{
  "Action": "ListUK8SULSConfigResponse",
  "ClusterId": "rAtMbQFa",
  "ExtractRule": {},
  "InputDetail": {},
  "MatchRule": {},
  "Name": "FvhXSZnH",
  "RetCode": 0,
  "TopicId": "xZhaZWGY"
}
```





