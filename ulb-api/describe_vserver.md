# 获取VServer信息 - DescribeVServer

## 简介

获取ULB下的VServer的详细信息



!> VServerId 对应 CreateVServer 返回的 VServerId<br />或者 DescribeULB 返回的 ULBVServerSet 中的 VServerId


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVServer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 负载均衡实例的Id |No|
| **VServerId** | string | VServer实例的Id；若指定则返回指定的VServer实例的信息； 若不指定则返回当前负载均衡实例下所有VServer的信息 |No|
| **Limit** | int | 数据分页值 |No|
| **Offset** | int | 数据偏移量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的VServer总数 |No|
| **DataSet** | array[[*ULBVServerSet*](#ULBVServerSet)] | VServer列表，每项参数详见 ULBVServerSet |No|

#### 数据模型


#### ULBVServerSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MonitorType** | string | 健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；Ping -> Ping探测， Customize -> UDP检查<br /><br />请求代理型默认值为Port，其中TCP协议仅支持Port，其他协议支持Port和Path; 报文转发型TCP协议仅支持Port，UDP协议支持Ping、Port和Customize |**Yes**|
| **PersistenceType** | string | VServer会话保持方式。枚举值为： None -> 关闭会话保持； ServerInsert -> 自动生成； UserDefined -> 用户自定义。 |**Yes**|
| **ULBId** | string | 负载均衡实例的Id |No|
| **Domain** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查域名 |No|
| **Path** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查路径 |No|
| **RequestMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查发出的请求报文 |No|
| **ResponseMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查请求应收到的响应报文 |No|
| **VServerId** | string | VServer实例的Id |No|
| **VServerName** | string | VServer实例的名字 |No|
| **Protocol** | string | VServer实例的协议。 枚举值为：HTTP，TCP，UDP，HTTPS。 |No|
| **FrontendPort** | int | VServer服务端口 |No|
| **Method** | string | VServer负载均衡的模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）。 |No|
| **PersistenceInfo** | string | 根据PersistenceType确定： None或ServerInsert，此字段为空； UserDefined，此字段展示用户自定义会话string。 |No|
| **ClientTimeout** | int | 空闲连接的回收时间，单位：秒。 |No|
| **Status** | int | VServer的运行状态。枚举值： 0 -> rs全部运行正常;1 -> rs全部运行异常；2 -> rs部分运行异常。 |No|
| **SSLSet** | array[[*ULBSSLSet*](#ULBSSLSet)] | VServer绑定的SSL证书信息，具体结构见下方 ULBSSLSet。 |No|
| **BackendSet** | array[[*ULBBackendSet*](#ULBBackendSet)] | 后端资源信息列表，具体结构见下方 ULBBackendSet |No|
| **ListenType** | string | 监听器类型，枚举值为: RequestProxy -> 请求代理；PacketsTransmit -> 报文转发 |No|
| **PolicySet** | array[[*ULBPolicySet*](#ULBPolicySet)] | 内容转发信息列表，具体结构见下方 ULBPolicySet |No|
| **EnableCompression** | int | 数据压缩开关，0:关闭 1:开启 |No|
| **SecurityPolicy** | [*BindSecurityPolicy*](#BindSecurityPolicy) | VServer绑定的安全策略,具体结构见BindSecurityPolicy |No|
| **ForwardPort** | int | 重定向端口，取值范围[0-65535]；默认值为0，代表关闭；仅HTTP协议支持开启重定向功能 |No|
| **EnableHTTP2** | int | 0:关闭 1:开启，用于开启http2功能；默认值为0 |No|

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
| **SSLSource** | int | SSL证书来源，SSL证书来源，0代表证书来自于ULB平台，1代表证书来自于USSL平台 |No|
| **USSLId** | string | USSL证书平台的编号,只有当SSLSource为1时才出现 |No|
| **Domains** | string | USSL证书平台的域名,只有当SSLSource为1时才出现 |No|
| **NotBefore** | int | 证书颁发时间,只有当SSLSource为1时才出现 |No|
| **NotAfter** | int | 证书过期时间,只有当SSLSource为1时才出现 |No|

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
| **Weight** | int | 后端RS权重（在加权轮询算法下有效） |No|
| **VPCId** | string | 后端服务器所在的VPC |No|

#### ULBPolicySet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainMatchMode** | string | 内容转发规则中域名的匹配方式。枚举值：Regular，正则；Wildcard，泛域名	 |No|
| **PolicyId** | string | 内容转发Id，默认内容转发类型下为空。 |No|
| **PolicyType** | string | 内容类型，枚举值：Custom -> 客户自定义；Default -> 默认内容转发 |No|
| **Type** | string | 内容转发匹配字段的类型，枚举值：Domain -> 域名；Path -> 路径； 默认内容转发类型下为空 |No|
| **Match** | string | 内容转发匹配字段;默认内容转发类型下为空。 |No|
| **PolicyPriority** | int | 内容转发优先级，范围[1,9999]，数字越大优先级越高。默认内容转发规则下为0。 |No|
| **VServerId** | string | 所属VServerId |No|
| **TotalCount** | int | 默认内容转发类型下返回当前rs总数 |No|
| **BackendSet** | array[[*PolicyBackendSet*](#PolicyBackendSet)] | 内容转发下rs的详细信息，参考PolicyBackendSet |No|

#### BindSecurityPolicy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecurityPolicyId** | string | 安全策略组ID |No|
| **SecurityPolicyName** | string | 安全策略组名称 |No|
| **TLSVersion** | string | TLS最低版本 |No|
| **SSLCiphers** | array[string] | 加密套件 |No|
| **SecurityPolicyType** | int | 安全策略类型 0：预定义 1：自定义 |No|

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
https://api.ucloud.cn/?Action=DescribeVServer
&Region=KYqxsypJ
&ProjectId=GsYJSKSC
&ULBId=gWhpMvaT
&VServerId=KyxsohIo
&Limit=2
&Offset=6
```

### 响应示例
    
```json
{
  "Action": "DescribeVServerResponse",
  "DataSet": [
    {
      "BackendSet": [
        {
          "BackendId": "backend-XXX",
          "Enabled": 1,
          "Port": 80,
          "PrivateIP": "10.25.XX.17",
          "ResourceId": "uhost-XXXX",
          "ResourceName": "test",
          "ResourceType": "UHost",
          "Status": 0,
          "SubnetId": "subnet-XXXXX"
        }
      ],
      "ClientTimeout": 60,
      "CreateTime": 1529909432,
      "Domain": "",
      "EnableCompression": 1,
      "EnableHTTP2": 1,
      "ForwardPort": 4,
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
              "ObjectId": "b47f082b-684f-4d5c-8dc4-XXXX",
              "Port": 80,
              "PrivateIP": "10.25.XX.17",
              "ResourceName": "test"
            }
          ],
          "Match": "",
          "PolicyId": "",
          "PolicyPriority": 0,
          "PolicyType": "Default",
          "TotalCount": 1,
          "Type": "",
          "VServerId": "vserver-XXXXX"
        }
      ],
      "Protocol": "HTTP",
      "SSLSet": [],
      "SecurityPolicy": {},
      "Status": 0,
      "ULBId": "ulb-XXX",
      "VServerId": "vserver-XXX",
      "VServerName": "VServer"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





