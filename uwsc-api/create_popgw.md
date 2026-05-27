# 创建UWAN虚拟路由器 - CreatePOPGW

## 简介

创建UWAN虚拟路由器






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreatePOPGW)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreatePOPGW`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BWConf.Name** | string | 带宽的名称 |**Yes**|
| **BWConf.PayMode** | string | 带宽的计费方式，取值：<br />- fixed-bw：固定带宽计费；<br />- traffic：流量计费。 |**Yes**|
| **BWConf.BwMax** | float | UWAN 网关的带宽规格。取值：1-100。单位：Mbps。 |**Yes**|
| **BWConf.ChargeType** | string | 付费方式，枚举值：<br />- Month：月付；<br />- Year：年付；<br />- Postpadi：后付费（仅支持流量计费方式） |**Yes**|
| **BWConf.Quantity** | float | 带宽购买时长，默认为 0，代表有效期至月底 |No|
| **BWConf.ProductId** | int | 产品 ID |No|
| **BWConf.CouponId** | string | 优惠券 ID |No|
| **BWConf.Remark** | string | 带宽包备注信息 |No|
| **BWConf.BwType** | string | 带宽类型，默认为空字符串 |No|
| **Name** | string | 资源名称 |**Yes**|
| **Quantity** | int | UWAN 网关的购买时长，默认为 0，代表有效期至月底。(保持和BWConf.Quantity 相同) |**Yes**|
| **Remark** | string | 资源备注信息 |No|
| **ChargeType** | string | 付费方式, 枚举值为: <br />- Year：按年付费; <br />- Month:  按月付费；<br />(月付非必填，默认为 0；年付必填。) |No|
| **Type** | string | 入网类型，仅支持“IPSec” |No|
| **CouponId** | string | 代金券ID, 默认不使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PopGwId** | string | UWAN 网关实例 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreatePOPGW
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ooBHFwrY
&BWConf=LVGDeccZ
&Name=nzIGigtj
&Remark=YZbsMKff
&ChargeType=ASVnzGkn
&Quantity=2
&CouponId=lrMZyetr
&Spesc=gMQxswqj
&ChargeType=fpbFMLzs
&Quantity=2
&CouponId=GaqiZhYK
&Specs=TIOEalDb
&ChargeType=DqBbJGMQ
&Quantity=7
&CouponId=MdAnpCwk
&Type=GDyoAUuH
&BWConf.PayMode=RDRcGbJl
&BWConf.BwMax=3
&BWConf.ChargeType=Year
&BWConf.Quantity=3.64596
&BWConf.ProductId=1
&BWConf.CouponId=BgFFNxER
&BWConf.Remark=kMGBuVQi
&BWConf.BwType=atWrGOQe
```

### 响应示例
    
```json
{
  "Action": "CreatePOPGWResponse",
  "Message": "qtfEvfGP",
  "PopGwId": "kamFBVCe",
  "RetCode": 0
}
```





