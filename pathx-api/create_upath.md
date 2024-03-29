# 创建UPath - CreateUPath

## 简介

创建UPath

?> LineId参数范围 从DescribePathXLineConfig接口获取。资源创建后，会开启自动续费，账户剩余额度不足则会产生欠费订单直到资源被回收。注意开启后付费的资源，每日流量费用日结，如果超过七天扣费失败会限制带宽为1mbps




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUPath)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUPath`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 名字，便于记忆区分 |**Yes**|
| **LineId** | string | 选择的线路，由DescribePathXLineConfig接口提供 |**Yes**|
| **Bandwidth** | int | 当PostPaid为false时，该值为预付费固定带宽；当PostPaid为true时，该值为后付费保底带宽，保底带宽越大可用的上限带宽越大。最小1Mbps,最大带宽由 DescribePathXLineConfig 接口获得。可联系产品团队咨询最大带宽。 |**Yes**|
| **ChargeType** | string | 计费模式，默认为Month 按月收费,可选范围['Month','Year','Dynamic'] |No|
| **Quantity** | int | 购买周期，ChargeType为Month时，Quantity默认为0代表购买到月底，按时和按年付费该参数必须大于0 |No|
| **PostPaid** | boolean | 是否开启后付费, 默认为false ，不开启后付费。当ChargeType为Dynamic时不能开启后付费。 |No|
| **PathType** | string | private:专线线路；public:海外SD-WAN。默认为private。 |No|
| **CouponId** | string | 代金券Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PathId** | string | 加速线路实例Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUPath
&Name=test
&LineId=line_cn_afr-nigeria
&Bandwidth=1
&ChargeType=Month
&Quantity=0
&CouponId=
&PostPaid=true
&PathType=HAqxnycJ
```

### 响应示例
    
```json
{
  "Action": "CreateUPathResponse",
  "RetCode": 0,
  "UPathId": "upath-xxx"
}
```





