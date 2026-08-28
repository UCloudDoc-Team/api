# 创建 UK8S 日志采集配置 - CreateUK8SULSConfig

## 简介

创建 LogConfig 自定义资源，用于声明式地定义日志采集规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUK8SULSConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TopicID** | string | 日志服务中用于接收日志的目标 Topic ID。 |**Yes**|
| **ClusterId** | string | UK8S 集群ID。 |**Yes**|
| **Name** | string | 要创建的日志的采集规则的名称，不能重复。总长度不能超过 253个字符。字符类型：只能包含小写字母（a-z）、数字（0-9）、破折号（-）和点（.）。开头和结尾字符：必须以小写字母或数字开头，并且也必须以小写字母或数字结尾。不允许以 - 或 . 开头或结尾。连续特殊字符：不能连续出现点（.）或破折号（-）。 |**Yes**|
| **ExtractRule.LogType** | string | 日志解析类型，决定了如何结构化日志。可选值: multi_line_delimiter：多行分隔符，delimiter:分隔符，full_regex:完全正则，multi_line_full_regex:多行完全正则，minimal_list:单行全文日志,multi_line:多行全文日志 |**Yes**|
| **ExtractRule.CollectPolicy** | string | 采集策略。可选值: full (全量采集存量日志), increment (从当前时间点增量采集)。默认为 full。 |No|
| **ExtractRule.Encode** | string | 日志原文的编码格式。可选值: utf-8, gbk。默认为 utf-8。 |No|
| **ExtractRule.Keys.N** | string | 当LogType 为分隔符、正则、多行正则时可用 |No|
| **ExtractRule.Delimiter** | string | 当 LogType 为delimiter 时可选，接收 "space"、"tab"、"\|"、";"、","。 |No|
| **ExtractRule.BeginningRegex** | string | 行首正则表达式。当 logType 为多行模式 (如 multi_line 或 multi_line_full_regex) 时，用于标识一条新日志的开始。 |No|
| **ExtractRule.LogRegex** | string | 日志提取正则表达式。当 logType 为正则模式 (如 full_regex,multi_line_full_regex) 时，用于从日志中提取字段。 |No|
| **ExtractRule.ExtractRule.LogRegexBase64** | string | Base64 编码的日志提取正则表达式。 |No|
| **ExtractRule.TimeKey** | string | 当日志为 json 或正则提取时，指定包含日志时间的字段名 (Key)。 |No|
| **ExtractRule.TimeFormat** | string | timeKey 对应的时间格式。 |No|
| **ExtractRule.UnMatchUpload** | string | 是否上传解析失败的日志。true 表示上传，false 表示丢弃。默认为 false。 |No|
| **ExtractRule.UnMatchKey** | string | 没有设置默认值；UnMatchUpload="true" 时强制要求填写 |No|
| **ExtractRule.DelimiterBase64** | string | Base64 编码的分隔符，优先级高于 Delimiter |No|
| **ExtractRule.BeginningRegexBase64** | string | Base64 编码的行首正则，优先级高于 BeginningRegex |No|
| **InputDetail.Type** | string | 日志输入类型。支持 container_file 和 container_stdout |**Yes**|
| **InputDetail.Metadata.Container** | string | 指定具体要采集元数据的容器名。如果留空，则不采集容器的元数据,可选字段：container_name,namespace,pod_name,pod_ip,pod_uid,container_id,image_name。Pod Label 元数据通过指定 InputDetail.Metadata.Labels字段。 |No|
| **InputDetail.Metadata.Labels** | string | 定义要采集哪些 Pod 的标签 (Labels)。可选值: * (采集所有标签), "app,version" (仅采集 app 和 version), "" (不采集任何标签)。 |No|
| **InputDetail.FilePaths.N.Path** | string | 定义采集路径 |No|
| **InputDetail.FilePaths.N.File** | string | 定义采集路径的文件名 |No|
| **InputDetail.Stream** | string | all、stdout、stderr，默认 all (用于 InputDetail.Type = container_stdout) |No|
| **MatchRule.ContainerOperator** | string | 容器名称匹配操作符。支持：in(包含)，notin(不包含) |No|
| **MatchRule.Container** | string | 要匹配的容器名称，*表示所有容器，用逗号分隔 |No|
| **MatchRule.Workloads.N.Namespace** | string | 按工作负载匹配时，工作负载所在的命名空间。 |No|
| **MatchRule.Workloads.N.Type** | string | 按工作负载匹配时，工作负载的类型，例如 deployment, statefulset, daemonset,job, cronjob。 |No|
| **MatchRule.Workloads.N.Name** | string | 按工作负载匹配时，工作负载的名称。 |No|
| **MatchRule.PodLabels.NamespaceOperator** | string | 指定/排除命名空间, 可选值: in/notin |No|
| **MatchRule.PodLabels.Namespace** | string | 命名空间名称 |No|
| **MatchRule.PodLabels.Labels.N.Key** | string | 按 Pod 标签匹配时，要匹配的标签的 Key。 |No|
| **MatchRule.PodLabels.Labels.N.ValueOperator** | string | 按 Pod 标签匹配时，标签值的匹配操作符。可选值: in, notin。 |No|
| **MatchRule.PodLabels.Labels.N.Value** | string | 按 Pod 标签匹配时，要匹配的标签的值。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUK8SULSConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=mTnJmhCk
&TopicID=cqGyMBwY
&ClusterId=lPgkrLoJ
&Name=enInlmdd
&ExtractRule.CollectPolicy=QphbYQti
&ExtractRule.Encode=RuByGGvP
&ExtractRule.LogType=vYDqTxpK
&ExtractRule.Delimiter=IxmsBKsf
&ExtractRule.BeginningRegex=IxBhFvBs
&ExtractRule.LogRegex=pligMTOZ
&ExtractRule.TimeKey=mOJXezrH
&ExtractRule.TimeFormat=QmwFYCWv
&ExtractRule.UnMatchKey=LdqdHiQH
&InputDetail.Type=TvAAKaZP
&InputDetail.Metadata.Container=goOfNbDg
&InputDetail.Metadata.Labels=kRJiYEVE
&InputDetail.FilePaths.N.Path=VibkGFGP
&InputDetail.FilePaths.N.File=HgHAjDVy
&MatchRule.ContainerOperator=scACWcjc
&MatchRule.Container=CLAdBtkp
&MatchRule.Workloads.N.Namespace=uqEDfRoq
&MatchRule.Workloads.N.Type=lOlATquw
&MatchRule.Workloads.N.Name=mpUqyauJ
&MatchRule.PodLabels.Labels.N.Key=JCcfOwru
&MatchRule.PodLabels.Labels.N.ValueOperator=GToTTBYN
&MatchRule.PodLabels.Labels.N.Value=jParVLLk
&ExtractRule.Keys.N=nJoumoAU
&MatchRule.PodLabels.NamespaceOperator=kLXDvrHF
&MatchRule.PodLabels.Namespace=mDUOTtSy
&ExtractRule.DelimiterBase64=IlmwgKSc
&ExtractRule.BeginningRegexBase64=zShzqdlg
&InputDetail.Stream=qdJuMqDK
&ExtractRule.ExtractRule.LogRegexBase64=bTzjHNBB
```

### 响应示例
    
```json
{
  "Action": "CreateUK8SULSConfigResponse",
  "RetCode": 0
}
```





