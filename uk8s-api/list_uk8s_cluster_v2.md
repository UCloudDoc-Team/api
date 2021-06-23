# 获取UK8S集群信息 - ListUK8SClusterV2

## 简介

获取UK8S集群列表信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUK8SClusterV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 列表起始位置偏移量，默认为0。 |No|
| **Limit** | int | 返回数据长度，默认为20。 |No|
| **ClusterId** | string | UK8S集群ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterCount** | int | 满足条件的集群数量 |**Yes**|
| **ClusterSet** | array[[*ClusterSet*](#ClusterSet)] | 集群信息，具体参考ClusterSet |No|

#### 数据模型


#### ClusterSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClusterName** | string | 资源名字 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **VPCId** | string | 所属VPC |**Yes**|
| **SubnetId** | string | 所属子网 |**Yes**|
| **PodCIDR** | string | Pod网段 |**Yes**|
| **ServiceCIDR** | string | 服务网段 |**Yes**|
| **MasterCount** | int | Master 节点数量 |**Yes**|
| **ApiServer** | string | 集群apiserver地址 |**Yes**|
| **K8sVersion** | string | 集群版本 |**Yes**|
| **ClusterLogInfo** | string | 创建集群时判断如果为NORESOURCE则为没资源，否则为空 |**Yes**|
| **CreateTime** | int | 创建时间 |No|
| **NodeCount** | int | Node节点数量 |No|
| **ExternalApiServer** | string | 集群外部apiserver地址	 |No|
| **Status** | string | 集群状态，枚举值：初始化："INITIALIZING"；启动中："STARTING"；创建失败："CREATEFAILED"；正常运行："RUNNING"；添加节点："ADDNODE"；删除节点："DELNODE"；删除中："DELETING"；删除失败："DELETEFAILED"；错误："ERROR"；升级插件："UPDATE_PLUGIN"；更新插件信息："UPDATE_PLUGIN_INFO"；异常："ABNORMAL"；升级集群中："UPGRADING"；容器运行时切换："CONVERTING" |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUK8SClusterV2
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jrVZnyEh
&Offset=5
&Limit=4
&ClusterId=DiFSEdqw
```

### 响应示例
    
```json
{
  "Action": "ListUK8SClusterV2Response",
  "ClusterCount": 7,
  "ClusterSet": [
    {
      "ApiServer": "lCABdaWT",
      "ClusterId": "SciLLuOV",
      "ClusterName": "qsKUTmxo",
      "CreateTime": 2,
      "ExternalApiServer": "vZfLtCWo",
      "K8sVersion": "KuiydQsJ",
      "MasterCount": 2,
      "NodeCount": 1,
      "PodCIDR": "NtUEVnsd",
      "ServiceCIDR": "yURWbTOO",
      "Status": "cbTawLFM",
      "SubnetId": "qizOyyNS",
      "VPCId": "tkoNZSem"
    }
  ],
  "RetCode": 0
}
```





