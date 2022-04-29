# 获取云手机服务器价格 - GetUPhoneServerPrice

## 简介

根据服务器规格名称，获取UPhoneServer实例的价格。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPhoneServerPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ServerModelName** | string | 服务器规格名称 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为：<br /><br />> Year，按年付费；<br /><br />> Month，按月付费；<br /><br />> Dynamic，按小时预付费; <br />如果不传某个枚举值，默认返回年付、月付的价格组合集。 |No|
| **Quantity** | int | 购买时长。默认: 1。 月付时，此参数传0，代表了购买至月末。 |No|
| **IpDestRegion** | string | 购买独立IP必须此参数。绑定的目的地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Bandwidth** | int | 购买独立IP需要此参数。共享带宽总值。 |No|
| **IpCount** | int | 购买独立IP需要此参数。需要的eip数量。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UPhoneServerPriceSet*](#UPhoneServerPriceSet)] | 价格列表，每项参数见UPhoneServerPriceSet |**Yes**|

#### 数据模型


#### UPhoneServerPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，枚举值：Year，Month |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字	 |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）	 |**Yes**|
| **ListPrice** | float | 产品列表价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPhoneServerPrice
&Region=cn-zj
&ProjectId=hBETKWYu
&Cpu=1
&Memory=3
&Disks.N.IsBoot=yiLUAKKj
&Disks.N.Size=8
&Disks.N.Type=eqHvqZDl
&GpuType=UXyykBgN
&GPU=YPiaCFel
&ChargeType=mciTPKdE
&Quantity=9
&ServerModelName=XMGpPUgb
&CityId=EpJYRmTC
&Bandwidth=3
&IpCount=2
&Bandwidth=8
&IpCount=7
&IpDestRegion=ZNmumMfW
```

### 响应示例
    
```json
{
  "Action": "GetUPhoneServerPriceResponse",
  "Message": "XznplJEy",
  "PriceSet": [
    {
      "ChargeType": "qhaUzzNy",
      "ListPrice": 8.55758,
      "OriginalPrice": 1.16836,
      "Price": 3.52512
    }
  ],
  "RetCode": 0
}
```





