# 获取负载均衡信息 - DescribeULBSimple

## 简介

获取ULB信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeULBSimple)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULBSimple`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 数据分页值，默认为10000 |No|
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
| **TotalCount** | int | 满足条件的ULB总数 |**Yes**|
| **DataSet** | array[[*ULBSimpleSet*](#ULBSimpleSet)] | ULB列表，每项参数详见 ULBSimpleSet |**Yes**|

#### 数据模型


#### ULBSimpleSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ListenType** | string | ULB 监听器类型，枚举值：RequestProxy，请求代理； PacketsTransmit ，报文转发；Comprehensive，兼容型；Pending，未定型 |**Yes**|
| **IPVersion** | string | ULB提供服务的IP类型。枚举值，“IPv4”,"IPv6"。默认为“IPv4” |**Yes**|
| **SnatIps** | array[string] | ULB后向代理IP，仅当有代理IP时返回<br />否 |No|
| **ULBId** | string | 负载均衡的资源ID<br /> |No|
| **Name** | string | 负载均衡的资源名称 |No|
| **Tag** | string | 负载均衡的业务组名称 |No|
| **Remark** | string | 负载均衡的备注 |No|
| **CreateTime** | int | ULB的创建时间，格式为Unix Timestamp |No|
| **VPCId** | string | ULB所在的VPC的ID |No|
| **SubnetId** | string | ULB 为 InnerMode 时，ULB 所属的子网ID |No|
| **BusinessId** | string | ULB 所属的业务组ID |No|
| **PrivateIP** | string | ULB的内网IP，当ULBType为OuterMode时，该值为空<br /> |No|
| **BandwidthType** | int | 带宽类型，枚举值为： 0，非共享带宽； 1，共享带宽<br /> |No|
| **Bandwidth** | int | 带宽 |No|
| **IPSet** | array[[*ULBIPSet*](#ULBIPSet)] | ULB的详细信息列表，具体结构见下方 ULBIPSet |No|
| **VServerCount** | int | ulb下vserver数量 |No|
| **ULBType** | string | ULB 的类型（InnerMode or OuterMode） |No|
| **FirewallSet** | array[[*FirewallSet*](#FirewallSet)] | 防火墙信息，具体结构见下方 FirewallSet |No|
| **EnableLog** | int | ULB是否开启日志功能。0，关闭；1，开启 |No|
| **LogSet** | [*LoggerSet*](#LoggerSet) | 日志功能相关信息，仅当EnableLog为true时会返回，具体结构见下方 LoggerSet |No|
| **WAFMode** | string | WAF功能状态，枚举类型：Unavailable：无法创建WAF；NoWAF：未绑定WAF；Intranet：内网回源Waf；Extranet：外网回源Waf |No|

#### ULBIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 弹性IP的运营商信息，枚举值为：  Bgp：BGP IP International：国际IP |No|
| **EIP** | string | 弹性IP地址 |No|
| **EIPId** | string | 弹性IP的ID |No|
| **BandwidthType** | int | 弹性IP的带宽类型，枚举值：1 表示是共享带宽，0 普通带宽类型（暂未对外开放） |No|
| **Bandwidth** | int | 弹性IP的带宽值（暂未对外开放） |No|

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

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULBSimple
&Region=NkZeYzgW
&ProjectId=COkbjaiz
&Offset=1
&Limit=RCMgySOS
&ULBId=eqSdcAVR
&VPCId=hDOcNuBP
&SubnetId=GbnHwPJO
&BusinessId=jWjuaUUB
```

### 响应示例
    
暂无





