# 创建轻量应用云主机 - CreateULHostInstance

## 简介

创建轻量应用云主机









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateULHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageId** | string | 镜像ID。 请通过 [DescribeImage](api/uhost-api/describe_image)获取 |**Yes**|
| **BundleId** | string | 套餐ID。如："ulh.c1m1s40b30t800" |**Yes**|
| **Password** | string | ULHost密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，举例如下：# echo -n Password1 \| base64 |**Yes**|
| **Name** | string | 轻量应用主机名称。默认：套餐ID。请遵照[字段规范](api/uhost-api/specification)设定实例名称。 |No|
| **ChargeType** | string | 计费模式。枚举值： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；默认：Month |No|
| **Quantity** | int | 购买时长。默认：1。不支持购买到月末 |No|
| **CouponId** | string | 主机代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ULHostId** | string | 实例ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateULHostInstance
&Region=cn-zj
&ProjectId=BiVhUqWM
&BundleId=WKrqUTuj
&ChargeType=iHquSVAk
&Password=KzuuLxoH
&Quantity=4
&Quantity=8
&ImageId=reBHwafg
&ImageId=qCkNplRb
&CouponId=JsBRKuuV
&ImageId=MmsUzsUT
&CouponId=ymmIIHOA
&BillActivityId=8
&BillActivityRuleId=6
&Name=dtIbqVbo
```

### 响应示例
    
```json
{
  "Action": "CreateULHostInstanceResponse",
  "Message": "UQIsLeri",
  "RetCode": 0,
  "ULHostId": "DJCRwHar"
}
```





