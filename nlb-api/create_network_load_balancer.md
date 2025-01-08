# 创建网络型负载均衡 - CreateNetworkLoadBalancer

## 简介

创建网络型负载均衡






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateNetworkLoadBalancer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNetworkLoadBalancer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPCId** | string | 载均衡实例所属的VPC资源ID |**Yes**|
| **SubnetId** | string | 负载均衡实例所属的子网资源ID |**Yes**|
| **ApiVersion** | string | API 版本，限定取值 "v1.0"/"v2.0"，默认值："v2.0" |No|
| **Tag** | string | 负载均衡实例所属的业务组ID |No|
| **Name** | string | 负载均衡实例的名称<br />限定字符长度：[1-255]<br />限定特殊字符，仅支持：-_.<br />默认值：nlb |No|
| **Remark** | string | 负载均衡实例的备注信息<br />限定字符长度：[0-255] |No|
| **IPVersion** | string | 负载均衡实例的IP协议，限定取值："IPv4"/"IPv6"/"DualStack"，默认值："IPv4" |No|
| **ChargeType** | string | 付费模式，限定取值："Dynamic"/"Month"/"Year" |No|
| **Quantity** | int | 购买的时长，ChargeType = "Month"，Quantity = 0 代表购买到月底，其余情况必须赋值 |No|
| **CouponId** | string | 代金券code	 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NLBId** | string | 返回的NLBId |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateNetworkLoadBalancer
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=HkjWDdfl
&VPCId=EssQuIsg
&SubnetId=vyYFxdTt
&Version=wJdyXLks
&Tag=AMKOemER
&Remark=bhMftnEX
&IPVersion=fVEAhtVI
&ChargeType=RflnbSTn
&Quantity=2
&CouponId=gnDIbnkQ
&Name=tFAHapTS
```

### 响应示例
    
```json
{
  "Action": "CreateNetworkLoadBalancerResponse",
  "Message": "cfTYWNPs",
  "NLBId": "gTFbefPL",
  "RetCode": 0
}
```





