# 获取云游戏城市列表 - DescribeUGameCities

## 简介

获取云游戏提供服务的城市列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGameCities`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGameCities** | array[[*CityInstance*](#CityInstance)] | 云手机城市实例列表，每项参数可见数据模型 [CityInstance] |**Yes**|
| **TotalCount** | int | 城市个数 |No|

#### 数据模型


#### CityInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-jinan |No|
| **CityName** | string | 城市名称，eg:上海二、济南市 |No|
| **IsSoldOut** | boolean | 表示该城市资源是否售罄 |No|
| **CityType** | string | 城市类型。枚举值：CENTER，中心城市，EDGE，边缘计算城市 |No|
| **CityAlias** | string | 城市别名。如cn-sh2 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGameCities
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=RpeYZAwK
```

### 响应示例
    
```json
{
  "Action": "DescribeUGameCitiesResponse",
  "Message": "YLrGvpod",
  "RetCode": 0,
  "TotalCount": 3,
  "UPhoneCities": [
    {
      "CityAlias": "qoORBsVT",
      "CityId": "uMDOrLPf",
      "CityName": "xWBQESVC",
      "CityType": "LUjtNTla",
      "IsSoldOut": true
    }
  ]
}
```





