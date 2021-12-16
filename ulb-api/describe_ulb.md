# 获取负载均衡信息 - DescribeULB

## 简介

获取ULB详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeULB)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULB`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 数据分页值，默认为20 |No|
| **ULBId** | string | 负载均衡实例的Id。 若指定则返回指定的负载均衡实例的信息； 若不指定则返回当前数据中心中所有的负载均衡实例的信息 |No|
| **VPCId** | string | ULB所属的VPC |No|
| **SubnetId** | string | ULB所属的子网ID |No|
| **BusinessId** | string | ULB所属的业务组ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的ULB总数 |No|
| **DataSet** | array[[*ULBSet*](#ULBSet)] | ULB列表，每项参数详见 ULBSet |No|

#### 数据模型


#### ULBSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ULBId** | string | 负载均衡的资源ID |No|
| **Name** | string | 负载均衡的资源名称 |No|
| **Tag** | string | 负载均衡的业务组名称 |No|
| **Remark** | string | 负载均衡的备注 |No|
| **BandwidthType** | int | 带宽类型，枚举值为： 0，非共享带宽； 1，共享带宽 |No|
| **Bandwidth** | int | 带宽 |No|
| **CreateTime** | int | ULB的创建时间，格式为Unix Timestamp |No|
| **IPSet** | array[[*ULBIPSet*](#ULBIPSet)] | ULB的详细信息列表，具体结构见下方 ULBIPSet |No|
| **VServerSet** | array[[*ULBVServerSet*](#ULBVServerSet)] | 负载均衡实例中存在的VServer实例列表，具体结构见下方 ULBVServerSet |No|
| **ULBType** | string | ULB 的类型 |No|
| **IPVersion** | string | ULB ip类型，枚举值：IPv6 / IPv4 （内部测试，暂未对外开放） |No|
| **ListenType** | string | ULB 监听器类型，枚举值：RequestProxy，请求代理； PacketsTransmit ，报文转发；Comprehensive，兼容型；Pending，未定型 |No|
| **VPCId** | string | ULB所在的VPC的ID |No|
| **SubnetId** | string | ULB 为 InnerMode 时，ULB 所属的子网ID，默认为空 |No|
| **BusinessId** | string | ULB 所属的业务组ID |No|
| **PrivateIP** | string | ULB的内网IP，当ULBType为OuterMode时，该值为空 |No|
| **FirewallSet** | array[[*FirewallSet*](#FirewallSet)] | 防火墙信息，具体结构见下方 FirewallSet |No|
| **EnableLog** | int | ULB是否开启日志功能。0，关闭；1，开启 |No|
| **LogSet** | [*LoggerSet*](#LoggerSet) | 日志功能相关信息，仅当EnableLog为true时会返回，具体结构见下方 LoggerSet |No|

#### ULBIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 弹性IP的运营商信息，枚举值为：  Bgp：BGP IP International：国际IP |No|
| **EIP** | string | 弹性IP地址 |No|
| **EIPId** | string | 弹性IP的ID |No|
| **BandwidthType** | int | 弹性IP的带宽类型，枚举值：1 表示是共享带宽，0 普通带宽类型（暂未对外开放） |No|
| **Bandwidth** | int | 弹性IP的带宽值（暂未对外开放） |No|

#### ULBVServerSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MonitorType** | string | 健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；Ping -> Ping探测， Customize -> UDP检查<br /><br />请求代理型默认值为Port，其中TCP协议仅支持Port，其他协议支持Port和Path; 报文转发型TCP协议仅支持Port，UDP协议支持Ping、Port和Customize |**Yes**|
| **ULBId** | string | 负载均衡实例的Id |**Yes**|
| **Domain** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查域名 |No|
| **Path** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查路径 |No|
| **RequestMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查发出的请求报文 |No|
| **ResponseMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查请求应收到的响应报文 |No|
| **VServerId** | string | VServer实例的Id |No|
| **VServerName** | string | VServer实例的名字 |No|
| **Protocol** | string | VServer实例的协议。 枚举值为：HTTP，TCP，UDP，HTTPS。 |No|
| **FrontendPort** | int | VServer服务端口 |No|
| **Method** | string | VServer负载均衡的模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）。 |No|
| **PersistenceType** | string | VServer会话保持方式。枚举值为： None -> 关闭会话保持； ServerInsert -> 自动生成； UserDefined -> 用户自定义。 |No|
| **PersistenceInfo** | string | 根据PersistenceType确定： None或ServerInsert，此字段为空； UserDefined，此字段展示用户自定义会话string。 |No|
| **ClientTimeout** | int | 空闲连接的回收时间，单位：秒。 |No|
| **Status** | int | VServer的运行状态。枚举值： 0 -> rs全部运行正常;1 -> rs全部运行异常；2 -> rs部分运行异常。 |No|
| **SSLSet** | array[[*ULBSSLSet*](#ULBSSLSet)] | VServer绑定的SSL证书信息，具体结构见下方 ULBSSLSet。 |No|
| **BackendSet** | array[[*ULBBackendSet*](#ULBBackendSet)] | 后端资源信息列表，具体结构见下方 ULBBackendSet |No|
| **ListenType** | string | 监听器类型，枚举值为: RequestProxy -> 请求代理；PacketsTransmit -> 报文转发 |No|
| **PolicySet** | array[[*ULBPolicySet*](#ULBPolicySet)] | 内容转发信息列表，具体结构见下方 ULBPolicySet |No|

#### FirewallSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FirewallName** | string | 防火墙名称 |No|
| **FirewallId** | string | 防火墙ID |No|

#### LoggerSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketName** | string | ulb日志上传的bucket |No|
| **TokenID** | string | 上传到bucket使用的token的tokenid |No|
| **TokenName** | string | bucket的token名称 |No|

#### ULBSSLSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | SSL证书的Id |No|
| **SSLName** | string | SSL证书的名字 |No|
| **SSLType** | string | SSL证书类型，暂时只有 Pem 一种类型 |No|
| **SSLContent** | string | SSL证书的内容 |No|
| **CreateTime** | int | SSL证书的创建时间 |No|
| **HashValue** | string | SSL证书的HASH值 |No|
| **BindedTargetSet** | array[[*SSLBindedTargetSet*](#SSLBindedTargetSet)] | SSL证书绑定到的对象 |No|

#### ULBBackendSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackendId** | string | 后端资源实例的Id |No|
| **ResourceType** | string | 资源实例的类型 |No|
| **ResourceId** | string | 资源实例的资源Id |No|
| **ResourceName** | string | 资源实例的资源名称 |No|
| **SubResourceType** | string | 资源绑定的虚拟网卡实例的类型 |No|
| **SubResourceId** | string | 资源绑定的虚拟网卡实例的资源Id |No|
| **SubResourceName** | string | 资源绑定的虚拟网卡实例的资源名称 |No|
| **PrivateIP** | string | 后端提供服务的内网IP |No|
| **Port** | int | 后端提供服务的端口 |No|
| **Enabled** | int | 后端提供服务的实例启用与否，枚举值：0 禁用 1 启用 |No|
| **Status** | int | 后端提供服务的实例运行状态，枚举值：0健康检查健康状态 1 健康检查异常 |No|
| **SubnetId** | string | 后端提供服务的资源所在的子网的ID |No|
| **IsBackup** | int | 是否为backup，只有当vserver的Backup属性为1时才会有此字段，说明：<br /><br />0：主rs<br />1：备rs |No|

#### ULBPolicySet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainMatchMode** | string | 内容转发规则中域名的匹配方式。枚举值：Regular，正则；Wildcard，泛域名	 |**Yes**|
| **PolicyId** | string | 内容转发Id，默认内容转发类型下为空。 |No|
| **PolicyType** | string | 内容类型，枚举值：Custom -> 客户自定义；Default -> 默认内容转发 |No|
| **Type** | string | 内容转发匹配字段的类型，枚举值：Domain -> 域名；Path -> 路径； 默认内容转发类型下为空 |No|
| **Match** | string | 内容转发匹配字段;默认内容转发类型下为空。 |No|
| **PolicyPriority** | int | 内容转发优先级，范围[1,9999]，数字越大优先级越高。默认内容转发规则下为0。 |No|
| **VServerId** | string | 所属VServerId |No|
| **TotalCount** | int | 默认内容转发类型下返回当前rs总数 |No|
| **BackendSet** | array[[*PolicyBackendSet*](#PolicyBackendSet)] | 内容转发下rs的详细信息，参考PolicyBackendSet |No|

#### PolicyBackendSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackendId** | string | 所添加的后端资源在ULB中的对象ID，（为ULB系统中使用，与资源自身ID无关 |No|
| **ResourceType** | string | 所添加的后端资源的类型，枚举值：UHost -> 云主机；UPM -> 物理云主机； UDHost -> 私有专区主机；UDocker -> 容器；UHybrid->混合云主机；CUBE->Cube；UNI -> 虚拟网卡 |No|
| **ResourceName** | string | 后端资源的实例名称 |No|
| **SubResourceId** | string | 如果资源绑定了弹性网卡，则展示弹性网卡的资源ID |No|
| **SubResourceName** | string | 如果资源绑定了弹性网卡，则展示弹性网卡的资源名称 |No|
| **SubResourceType** | string | "UNI"或者为空 |No|
| **ObjectId** | string | 后端资源的对象ID |No|
| **Port** | int | 所添加的后端资源服务端口 |No|
| **PrivateIP** | string | 后端资源的内网IP |No|

#### SSLBindedTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VServerId** | string | SSL证书绑定到的VServer的资源ID |No|
| **VServerName** | string | 对应的VServer的名字 |No|
| **ULBId** | string | VServer 所属的ULB实例的资源ID |No|
| **ULBName** | string | ULB实例的名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULB
&Region=cn-bj2
&ProjectId=project-XXXXX
```

### 响应示例
    
```json
{
  "Action": "DescribeULBResponse",
  "DataSet": [
    {
      "Bandwidth": 0,
      "BandwidthType": 0,
      "BusinessId": "",
      "CreateTime": 1529909322,
      "IPSet": [],
      "Name": "ULB",
      "PrivateIP": "",
      "Remark": "",
      "SubnetId": "",
      "Tag": "Default",
      "ULBId": "ulb-XXXX",
      "ULBType": "OuterMode",
      "VPCId": "uvnet-XXX",
      "VServerSet": [
        {
          "BackendSet": [
            {
              "BackendId": "backend-XXXX",
              "Enabled": 1,
              "Port": 80,
              "PrivateIP": "10.25.XXX.17",
              "ResourceId": "uhost-XXXX",
              "ResourceName": "test",
              "ResourceType": "UHost",
              "Status": 0,
              "SubnetId": "subnet-hi50vf"
            }
          ],
          "ClientTimeout": 60,
          "CreateTime": 1529909432,
          "Domain": "",
          "FrontendPort": 80,
          "ListenType": "RequestProxy",
          "Method": "Roundrobin",
          "MetricIdSet": [
            {
              "MetricId": "69538bf3-00bc-4385-85cc-XXXX",
              "Type": "OuterMode"
            }
          ],
          "MonitorType": "Port",
          "Path": "",
          "PersistenceInfo": "",
          "PersistenceType": "None",
          "PolicySet": [
            {
              "BackendSet": [
                {
                  "BackendId": "backend-XXXXX",
                  "ObjectId": "b47f082b-684f-4d5c-8dc4-XXXXX",
                  "Port": 80,
                  "PrivateIP": "10.25.XXX.17",
                  "ResourceName": "test"
                }
              ],
              "Match": "",
              "PolicyId": "",
              "PolicyPriority": 0,
              "PolicyType": "Default",
              "TotalCount": 1,
              "Type": "",
              "VServerId": "vserver-XXXX"
            }
          ],
          "Protocol": "HTTP",
          "SSLSet": [],
          "Status": 0,
          "VServerId": "vserver-XXXX",
          "VServerName": "VServer"
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





