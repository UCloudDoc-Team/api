# 查询集群插件信息 - GetUK8SPluginInfo

## 简介

查询集群插件信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SPluginInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterId** | string | 集群ID |**Yes**|
| **CNIInfoSet** | [*NodePlugin*](#NodePlugin) | CNI插件信息, 参看NodePlugin |**Yes**|
| **ClusterStatus** | string | 集群状态信息 |No|
| **ClusterUpgradeInfo** | [*ClusterUpgradeInfo*](#ClusterUpgradeInfo) | 集群升级相关信息 |No|
| **RuntimeConvertInfo** | [*RuntimeConvertInfo*](#RuntimeConvertInfo) | 集群容器运行时转换信息。 |No|
| **VKInfo** | [*VKNode*](#VKNode) | vk插件信息 |No|
| **CSIInfo** | [*CSIInfo*](#CSIInfo) | CSI 插件版本与状态。 |No|
| **CloudProviderInfo** | [*CloudProviderInfo*](#CloudProviderInfo) | CloudProvider 插件版本与状态。 |No|
| **MonitorInfo** | [*MonitorInfo*](#MonitorInfo) | 监控插件信息。 |No|

#### 数据模型


#### NodePlugin

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 插件名称, 如 CNI, CSI, Flexv, CloudProvider |**Yes**|
| **PluginInfoSet** | array[[*NodePluginInfo*](#NodePluginInfo)] | 各个节点插件信息, 参照NodePluginInfo |No|
| **AvailableVersion** | string | 最新插件版本 |No|
| **ReleaseTime** | string | 最新插件发布时间 |No|
| **ManageEnabled** | boolean | 插件管理是否开启 |No|

#### ClusterUpgradeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UpdateTime** | int | 集群信息更新时间戳，单位 s |No|
| **Stage** | string | string，集群升级所处阶段 Unknown、Precheck、MasterUpdating、NodeUpdating、Failed、Success<br /><br />集群从未进行过升级则返回 Unknown<br /><br />集群开始升级过程几个阶段 Precheck->MasterUpdating->NodeUpdating→Success<br /><br />如果升级失败则为 Failed |No|
| **Version** | string | string， 集群当前版本 |No|
| **TargetVersion** | string | string，集群升级目标版本 |No|
| **AvailableVersions** | array[string] | string 数组，可用新版本，例如  ["1.15.12","1.16.15","1.17.4","1.18.9"] |No|
| **NodeInfoSet** | array[[*ClusterUpdateNodeInfo*](#ClusterUpdateNodeInfo)] | 各个节点升级信息, 参照  ClusterUpdateNodeInfo |No|

#### RuntimeConvertInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeInfoSet** | array[[*NodePluginInfo*](#NodePluginInfo)] | 各节点的运行时转换状态。 |No|
| **Stage** | string | 集群从未进行过运行时转换则返回 Unknown<br /><br />集群运行时转换几个阶段 Precheck->Updating→Success<br /><br />如果转换失败则为 Failed |No|
| **UpdateTime** | int | 运行时转换信息更新时间，Unix 时间戳，单位秒。 |No|
| **RuntimeName** | string | 容器运行时名称。 |No|
| **RuntimeVersion** | string | 容器运行时版本。 |No|

#### VKNode

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 插件名称 |**Yes**|
| **PluginInfoSet** | array[[*VKNodeInfo*](#VKNodeInfo)] | 各虚拟节点的插件信息。 |No|
| **AvailableVersion** | string | 最新版本 |No|
| **ReleaseTime** | string | 发布时间 |No|
| **ManageEnabled** | boolean | 插件管理是否开启 |No|

#### CSIInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 插件名称。 |No|
| **AvailableVersion** | string | 最新可用插件版本。 |No|
| **ReleaseTime** | string | 最新可用版本的发布时间。 |No|
| **ManageEnabled** | boolean | 是否开启插件托管。 |No|
| **Version** | string | 当前插件版本。 |No|
| **Status** | int | 插件状态。 |No|
| **UpdateTime** | int | 更新时间，Unix 时间戳，单位秒。 |No|
| **OperationResult** | int | 上次插件操作结果。 |No|

#### CloudProviderInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 插件名称。 |No|
| **AvailableVersion** | string | 最新可用插件版本。 |No|
| **ReleaseTime** | string | 最新可用版本的发布时间。 |No|
| **ManageEnabled** | boolean | 是否开启插件托管。 |No|
| **Version** | string | 当前插件版本。 |No|
| **Status** | int | 插件状态。 |No|
| **UpdateTime** | int | 更新时间，Unix 时间戳，单位秒。 |No|
| **OperationResult** | int | 上次插件操作结果。 |No|

#### MonitorInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AvailableVersion** | string | 最新可用监控插件版本。 |No|

#### VKNodeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Node** | string | 节点 ID。 |No|
| **Version** | string | 插件版本。 |No|
| **Status** | int | 插件状态：0 未知，1 正常，2 异常，3 升级中。 |No|
| **UpdateTime** | int | 更新时间，Unix 时间戳，单位秒。 |No|
| **OperationResult** | int | 上次插件操作结果：0 无结果，1 查询成功，2 查询失败，3 升级成功，4 升级失败。 |No|

#### NodePluginInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Node** | string | Node节点名称 |**Yes**|
| **Version** | string | 插件版本 |No|
| **Status** | int | 插件工作状态，0：未知，1：正常，<br />2：异常, 3: 升级中 |No|
| **UpdateTime** | int | 插件信息更新时间 |No|
| **OperationResult** | int | 上次插件操作结果，0：没有上次操作结果，或当前正在执行升级或查询 1：获取成功 2 获取失败  3 升级成功 4 升级失败 |No|
| **IP** | string | Node节点IP |No|

#### ClusterUpdateNodeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Node** | string | Node节点名称 |**Yes**|
| **Version** | string | 插件版本 |No|
| **Status** | int | 插件工作状态，0：未知，1：正常，<br />2：异常, 3: 升级中 |No|
| **UpdateTime** | int | 插件信息更新时间 |No|
| **OperationResult** | int | 上次插件操作结果，0：没有上次操作结果，或当前正在执行升级或查询 1：获取成功 2 获取失败  3 升级成功 4 升级失败 |No|
| **IP** | string | Node节点IP |No|
| **Role** | string | 节点角色， master 或者 node |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SPluginInfo
&Region=cn-zj
&ProjectId=MPWlWQzv
&ClusterId=MIPAOUZL
```

### 响应示例
    
```json
{
  "Action": "GetUK8SPluginInfoResponse",
  "CNIInfoSet": {},
  "ClusterId": "JXboyKXh",
  "ClusterStatus": "aykUTAcj",
  "ClusterUpgradeInfo": {},
  "Message": "sKLavGzm",
  "RetCode": 0,
  "RuntimeConvertInfo": {},
  "VKInfo": {}
}
```





