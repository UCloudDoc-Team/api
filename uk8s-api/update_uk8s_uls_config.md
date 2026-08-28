# 更新UK8S日志采集配置 - UpdateUK8SULSConfig

## 简介

更新指定UK8S集群的日志采集规则。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUK8SULSConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表：https://docs.ucloud.cn/api/summary/regionlist |**Yes**|
| **Zone** | string | 可用区。参见地域和可用区列表：https://docs.ucloud.cn/api/summary/regionlist |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。请参考GetProjectList接口：https://docs.ucloud.cn/api/summary/get_project_list |No|
| **Name** | string | 要修改的日志采集规则名称。名称长度不能超过253个字符，只能包含小写字母、数字、破折号和点，并且必须以字母或数字开头和结尾。 |**Yes**|
| **ClusterId** | string | UK8S集群ID。 |**Yes**|
| **TopicID** | string | 日志服务中用于接收日志的目标Topic ID。不填写时保持原Topic ID不变。 |No|
| **ExtractRule.CollectPolicy** | string | 采集策略。可选值：full（全量采集存量日志）、increment（从当前时间点增量采集）。默认为full。 |No|
| **ExtractRule.Encode** | string | 日志原文的编码格式。可选值：utf-8、gbk。默认为utf-8。 |No|
| **ExtractRule.LogType** | string | 日志解析类型。可选值：json、delimiter、full_regex、multi_line_full_regex、multi_line_delimiter、minimal_list、multi_line。 |**Yes**|
| **ExtractRule.BeginningRegex** | string | 行首正则表达式。multi_line、multi_line_full_regex或multi_line_delimiter模式下，BeginningRegex和BeginningRegexBase64必须至少填写一个。 |No|
| **ExtractRule.BeginningRegexBase64** | string | Base64编码的行首正则表达式。填写时优先于BeginningRegex。 |No|
| **ExtractRule.LogRegex** | string | 日志提取正则表达式。full_regex或multi_line_full_regex模式下，LogRegex和LogRegexBase64必须至少填写一个。 |No|
| **ExtractRule.LogRegexBase64** | string | Base64编码的日志提取正则表达式。填写时优先于LogRegex。 |No|
| **ExtractRule.Delimiter** | string | 分隔符。delimiter或multi_line_delimiter模式下可用。可选值：space、tab、\|、;、,。 |No|
| **ExtractRule.DelimiterBase64** | string | Base64编码的分隔符。填写时优先于Delimiter。 |No|
| **ExtractRule.TimeKey** | string | 包含日志时间的字段名。 |No|
| **ExtractRule.TimeFormat** | string | TimeKey对应的时间格式。json、full_regex或multi_line_full_regex模式下，填写TimeKey时必须同时填写TimeFormat。 |No|
| **ExtractRule.UnMatchUpload** | string | 是否上传解析失败的日志。字符串true表示上传，false表示丢弃。默认为false。 |No|
| **ExtractRule.UnMatchKey** | string | 存放无法解析的日志原文的Key。UnMatchUpload为true时必须填写。 |No|
| **ExtractRule.Keys.N** | string | 提取后的字段名。仅适用于delimiter、full_regex、multi_line_full_regex和multi_line_delimiter。 |No|
| **InputDetail.Type** | string | 日志输入类型。可选值：container_file、container_stdout。 |**Yes**|
| **InputDetail.Stream** | string | 容器标准输出流类型。仅适用于container_stdout，可选值：all、stdout、stderr，默认为all。 |No|
| **InputDetail.Metadata.Container** | string | 要附加到日志中的容器元数据字段，多个字段使用逗号分隔。可选字段：container_name、namespace、pod_name、pod_ip、pod_uid、container_id、image_name。留空表示不采集容器元数据。 |No|
| **InputDetail.Metadata.Labels** | string | 要采集的Pod标签。*表示采集所有标签，app,version表示仅采集指定标签，空字符串表示不采集标签。 |No|
| **InputDetail.FilePaths.N.Path** | string | 日志采集路径。仅适用于container_file。 |No|
| **InputDetail.FilePaths.N.File** | string | 要采集的文件名。仅适用于container_file。 |No|
| **MatchRule.Container** | string | 要匹配的容器名称，*表示所有容器，多个名称使用逗号分隔。 |No|
| **MatchRule.ContainerOperator** | string | 容器名称匹配操作符。可选值：in、notin。填写该参数时必须同时填写MatchRule.Container。 |No|
| **MatchRule.Workloads.N.Namespace** | string | 按工作负载匹配时，工作负载所在的命名空间。Workloads和PodLabels不能同时设置。 |No|
| **MatchRule.Workloads.N.Type** | string | 工作负载类型。可选值：deployment、statefulset、daemonset、job、cronjob。 |No|
| **MatchRule.Workloads.N.Name** | string | 工作负载名称。 |No|
| **MatchRule.PodLabels.NamespaceOperator** | string | 按Pod标签匹配时，命名空间名称的匹配操作符。可选值：in、notin。填写该参数时必须同时填写MatchRule.PodLabels.Namespace。PodLabels和Workloads不能同时设置。 |No|
| **MatchRule.PodLabels.Namespace** | string | 按Pod标签匹配时要匹配的命名空间。 |No|
| **MatchRule.PodLabels.Labels.N.Key** | string | 按Pod标签匹配时，要匹配的标签Key。 |No|
| **MatchRule.PodLabels.Labels.N.ValueOperator** | string | 标签值匹配操作符。可选值：in、notin。 |No|
| **MatchRule.PodLabels.Labels.N.Value** | string | 要匹配的标签值。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUK8SULSConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ZnqHpvpN
&Namespace=YwrqqshI
&Name=sSFWIjLi
&TopicId=IaGDcAvd
&ExtractRule.CollectPolicy=mtLzGRYR
&ExtractRule.Encode=gGKxPoYw
&ExtractRule.LogType=mERxKFfi
&ExtractRule.BeginningRegex=hokZuFjj
&ExtractRule.LogRegex=slHfpSuK
&ExtractRule.TimeKey=ILmrJesk
&ExtractRule.TimeFormat=MhtusXpR
&ExtractRule.UnMatchKey=oWhCXqet
&InputDetail.Type=udiZMVEZ
&InputDetail.Metadata.Container=vAQhviWA
&InputDetail.Metadata.Labels=uqMsYkUu
&MatchRule.Workload.Namespace=FMvazeXw
&MatchRule.Workload.Type=NnSgvRfy
&MatchRule.Workload.Name=XRffJKle
&MatchRule.Workload.ContainerOperator=FQPUIFKU
&MatchRule.Workload.Container=hHgEbOrZ
&MatchRule.PodLabels.NamespaceOperator=rqCuYvEl
&MatchRule.PodLabels.Namespace=RUwMUnOM
&MatchRule.PodLabels.Labels.N.Key=pngxzLHq
&MatchRule.PodLabels.Labels.N.ValueOperator=UZgBMOms
&MatchRule.PodLabels.Labels.N.Value=AqvonjAA
&MatchRule.PodLabels.ContainerOperator=JomsSAaP
&MatchRule.PodLabels.Container=wbDGSafc
&ClusterId=fTqcIwOO
&ClusterId=YlVIkJMZ
&ExtractRule.Delimiter=HiYLmUuo
&InputDetail.Metadata.FilePaths.N.Path=GbdJICws
&InputDetail.Metadata.FilePaths.N.File=oOIkfmoj
&ExtractRule.Keys.N=IVYoDEhR
```

### 响应示例
    
```json
{
  "Action": "UpdateUK8SULSConfigResponse",
  "RetCode": 0
}
```





