# 创建应用型负载均衡实例 - CreateLoadBalancer

## 简介

创建一个应用型负载均衡实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateLoadBalancer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateLoadBalancer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | 负载均衡实例所属的VPC资源ID |**Yes**|
| **SubnetId** | string | 负载均衡实例所属的子网资源ID。<br />负载均衡实例的内网VIP和SNAT场景的源IP限定在该子网内；<br />指定子网不影响添加后端服务节点时的范围，依旧是整个VPC下支持的资源 |**Yes**|
| **Type** | string | 负载均衡实例的类型。限定枚举值："Application" / "Network"，默认值："Application" |No|
| **Name** | string | 负载均衡实例的名称。默认值：lb；特殊字符仅支持：“-”，“_”，“.”；限定字符长度：[1-255] |No|
| **Tag** | string | 负载均衡实例所属的业务组ID。默认值为“Default”； 传空则为Default业务组 |No|
| **Remark** | string | 负载均衡实例的备注信息。限定字符长度：[0-255] |No|
| **IPVersion** | string | 负载均衡实例的IP协议。限定枚举值："IPv4" / "IPv6"/"DualStack"，默认值为：“IPv4” |No|
| **ChargeType** | string | 付费模式。限定枚举值："Year" / "Month"/"Day"/"Dynamic"，默认值为：“Month” |No|
| **Quantity** | int | 购买的时长, 默认: 1; 0-> 购买至月末(0只在月付费有效，其余付费模式传0，实际收费按一个周期计费) |No|
| **SecGroups.N.SecGroupId** | string | 安全组id |No|
| **SecGroups.N.Priority** | int | 安全组优先级 |No|
| **LabelInfos.N.Key** | string | 标签键 |No|
| **LabelInfos.N.Value** | string | 标签值 |No|
| **CouponId** | string | 代金券code |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LoadBalancerId** | string | 负载均衡实例的ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateLoadBalancer
&Region=cn-bj2
&ProjectId=org-XXXXX
&VPCId=vnet-XXXXX
&SubnetId=subnet-XXXXX
&Type=Application
&Name=lb
&Tag=Default
&Remark=iKgxzEnT
&IPVersion=IPv4
&ChargeType=Month
&CouponId=KAxnpXFB
&Quantity=3
&SecGroups.n.SecGroupId=BnaEMYDa
&SecGroups.n.Priority=5
&LabelInfos.n.Key=klFzkSdb
&LabelInfos.n.Value=JYYmlWYL
```

### 响应示例
    
```json
{
  "Action": "CreateLoadBalancerResponse",
  "LoadBalancerId": "alb-XXXXX",
  "RetCode": 0
}
```





