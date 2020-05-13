# 获取路由表详细信息(包括路由策略) - DescribeRouteTable

## 简介

获取路由表详细信息(包括路由策略)





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeRouteTable)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeRouteTable`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **VPCId** | string | 所属VPC的资源ID |No|
| **RouteTableId** | string | 路由表资源ID |No|
| **OffSet** | int | 数据偏移量。默认为0 |No|
| **Limit** | int | 数据分页值。默认为20 |No|
| **BusinessId** | string | 业务组ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RouteTables** | array[[*RouteTableInfo*](#RouteTableInfo)] | 路由表信息 |No|
| **TotalCount** | int | RouteTables字段的数量 |No|

#### 数据模型


#### RouteTableInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RouteTableId** | string | 路由表资源ID |No|
| **RouteTableType** | int | 路由表类型。1为默认路由表，0为自定义路由表 |No|
| **SubnetCount** | int | 绑定该路由表的子网数量 |No|
| **VPCId** | string | 路由表所属的VPC资源ID |No|
| **VPCName** | string | 路由表所属的VPC资源名称 |No|
| **Tag** | string | 路由表所属业务组 |No|
| **Remark** | string | 路由表备注 |No|
| **CreateTime** | int | 创建时间戳 |No|
| **RouteRules** | array[[*RouteRuleInfo*](#RouteRuleInfo)] | 路由规则 |No|

#### RouteRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccountId** | int | 项目ID信息 |No|
| **DstAddr** | string | 目的地址 |No|
| **DstPort** | int | 保留字段，暂未使用 |No|
| **NexthopId** | string | 路由下一跳资源ID |No|
| **NexthopType** | string | 路由表下一跳类型。LOCAL，本VPC内部通信路由；PUBLIC，公共服务路由；CNAT，外网路由；UDPN，跨域高速通道路由；HYBRIDGW，混合云路由；INSTANCE，实例路由；VNET，VPC联通路由；IPSEC VPN，指向VPN网关的路由。 |No|
| **OriginAddr** | string | 保留字段，暂未使用 |No|
| **Priority** | int | 保留字段，暂未使用 |No|
| **Remark** | string | 路由规则备注 |No|
| **RouteRuleId** | string | 规则ID |No|
| **RouteTableId** | string | 路由表资源ID |No|
| **RuleType** | int | 路由规则类型。0，系统路由规则；1，自定义路由规则 |No|
| **SrcAddr** | string | 保留字段，暂未使用 |No|
| **SrcPort** | int | 保留字段，暂未使用 |No|
| **VNetId** | string | 所属的VPC |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeRouteTable
&ProjectId=org-test
&Region=cn-bj2
&VPCId=uvnet-test
&RouteTableId=routetable_test
&OffSet=0
&Limit=999
&BusinessId=PLFgRTxc
```

### 响应示例
    
```json
{
  "Action": "DescribeRouteTableResponse",
  "RetCode": 0
}
```





