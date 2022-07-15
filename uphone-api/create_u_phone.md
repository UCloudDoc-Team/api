# 创建云手机 - CreateUPhone

## 简介

创建云手机









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 云手机实例名称，默认：UPhone。如果同时创建多个，则增加数字后缀，如UPhone-1 |**Yes**|
| **UPhoneModelName** | string | 云手机规格名称，不超过64个字节。可通过[查询云手机规格列表]()查询支持的云手机规格。 |**Yes**|
| **MediaBandwidth** | int | 云手机画面带宽，默认2M |**Yes**|
| **ImageId** | string | 云手机镜像ID，不超过32个字节。可通过[查询手机镜像]()查询云手机规格对应的镜像ID。 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取<br /> |**Yes**|
| **UPhoneCount** | int | 创建云手机的个数 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： > 年 Year，按年付费； > Month，按月付费； > Dynamic，按小时预付费; 默认为月付 |No|
| **Quantity** | string | 购买时长。默认值: 1。月付时，此参数传0，代表购买至月末。 |No|
| **IpDestRegion** | string | 购买独立IP必须有此参数。绑定的目的地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Tag** | string | 业务组。默认：Default（Default即为未分组）。请遵照[字段规范](api/uhost-api/specification)设定业务组。 |No|
| **BindIp** | boolean | 绑定独立IP |No|
| **Bandwidth** | int | 共享带宽大小 |No|
| **IpProportion** | int | 独立IP参数。需要独立IP的比例。eg: [4:1]->4， [3:1]->3。 |No|
| **ShareBandwidthName** | string | 共享带宽名称，可以在创建新的共享带宽时指定一个名称 |No|
| **ShareBandwidthId** | string | 共享带宽ID，使用现有共享带宽时需要传入此参数 |No|
| **CouponId** | string | 云手机代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看。注：代金券对带宽不适用，仅适用于云手机计费 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 任务ID，用来查询创建云手机任务状态 |**Yes**|
| **UPhoneIds** | array[string] | 【数组】创建的云手机ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUPhone
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=GqDlziIx
&Name=CxZWlTZB
&UPhoneModelName=CVBorSMt
&ImageId=RXGPFOIk
&CityId=kXeOkMeu
&ChargeType=HMZKLhIW
&Quantity=YuNGrjCT
&IpDestRegion=YaNMiSss
&Tag=sQNkdGJy
&CouponId=osTxmdOn
&Count=8
&BindIp=false
&IndependentIpCouponId=PpUQMWSa
&IpGroupUuid=pdTAGgMl
&GroupUuid=GrgqJWmt
&IpProportion=3
&ShareBandwidthName=wcpbgZiX
&ShareBandwidthId=wSyprlze
```

### 响应示例
    
```json
{
  "Action": "CreateUPhoneResponse",
  "JobId": "XvgSYrEc",
  "Message": "QmAvYLMU",
  "RetCode": 0,
  "UPhoneIds": [
    "DWjsqMnS"
  ]
}
```





