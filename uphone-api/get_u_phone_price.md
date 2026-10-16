# 获取云手机价格 - GetUPhonePrice

## 简介

根据云手机规格名称，获取UPhone实例的价格。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPhonePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **UPhoneModelName** | int | 云手机规格名称 |No|
| **UPhoneCount** | int | 云手机个数 |No|
| **ChargeType** | string | 计费模式。枚举值为： > Year，按年付费； > Month，按月付费；> Day，按天付费； > Dynamic，按小时预付费; 如果不传某个枚举值，默认返回年付、月付的价格组合集。 |No|
| **Quantity** | int | 购买时长。默认: 1。 月付时，此参数传0，代表了购买至月末。 |No|
| **IpDestRegion** | string | 购买独立IP必须此参数。绑定的目的地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **INetBandwidth** | int | 购买独立IP需要此参数，其中一个ip的带宽值。 |No|
| **IpCount** | int | 购买独立IP需要此参数。需要的eip数量。 |No|
| **UseGlobalBws** | boolean | 使用全局共享带宽 |No|
| **BandwidthLine** | int | 购买独立IP并且使用全局共享带宽时需要此参数，带宽线路数量，与云手机数量一致 |No|
| **UPhoneBandwidth** | int | 单个云手机带宽大小，单位Kbps，仅在UseKbps为true时生效 |No|
| **UseKbps** | boolean | 使用Kbps单位带宽，仅在使用全局共享带宽时生效，值为true时BandwidthLine参数不再生效 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UPhonePriceSet*](#UPhonePriceSet)] | 价格列表，每项参数见UPhonePriceSet |**Yes**|

#### 数据模型


#### UPhonePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，枚举值：Year，Month，Dynamic |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字<br /> |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）<br /> |**Yes**|
| **ListPrice** | float | 产品列表价<br /> |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPhonePrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=qcSrMMvB
&CityId=tVtswLPD
&ServerModelName=eQqLiops
&ChargeType=ITyhotxM
&Quantity=7
&IpDestRegion=fSEWRrOB
&Bandwidth=3
&IpCount=1
&MediaBandwidth=9
&MediaBandwidth=8
&UPhoneCount=DHGufODz
&UseGlobalBws=true
&BandwidthLine=6
&UPhoneBandwidth=3
&UPhoneBandwidth=1
&UseKbps=true
&UseKbps=false
&UseKbps=false
```

### 响应示例
    
```json
{
  "Action": "GetUPhonePriceResponse",
  "PriceSet": "ZMgysDBT",
  "RetCode": 0
}
```





