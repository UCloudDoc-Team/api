# 检查轻量应用云主机资源余量 - CheckULHostResourceCapacity

## 简介

检查轻量应用云主机资源余量






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CheckULHostResourceCapacity`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageId** | string | 镜像ID。 请通过 [DescribeImage](api/uhost-api/describe_image)获取 |**Yes**|
| **BundleId** | string | 套餐ID。如："ulh.c1m1s40b30t800" |**Yes**|
| **Name** | string | 轻量应用主机名称。默认：套餐ID。请遵照[字段规范](api/uhost-api/specification)设定实例名称。 |No|
| **ChargeType** | string | 计费模式。枚举值： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > ThirtyDay，30天期付费，跨境电商相关套餐使用此计费方式；默认：Month |No|
| **Quantity** | int | 购买时长。默认：1。不支持购买到月末 |No|
| **VPCId** | string | VPC ID。默认为当前地域的默认VPC。 |No|
| **SubnetId** | string | 子网 ID。默认为当前地域的默认子网。 |No|
| **SecurityGroupId** | string | 防火墙ID，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeFirewall](api/unet-api/describe_firewall.html)。 |No|
| **CouponId** | string | 主机代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceEnough** | boolean | 资源是否充足<br /> |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CheckULHostResourceCapacity
&Region=cn-zj
&ProjectId=dkJFqRJJ
&ImageId=kBaGDyHc
&BundleId=EFKsULAJ
&Password=zmDlYNlz
&Name=bUBvNpbi
&ChargeType=lXBrlMtL
&Quantity=1
&VPCId=crUpJjJh
&SubnetId=cfTbEIRC
&SecurityGroupId=bCSqYcal
&BillActivityId=1
&BillActivityRuleId=2
&CouponId=LfMSIczn
```

### 响应示例
    
```json
{
  "Action": "CheckULHostResourceCapacityResponse",
  "Message": "YIZvrfmX",
  "RetCode": 0,
  "ULHostId": "tRoNqJfI"
}
```





