# 创建云游戏服务器 - CreateUGameServer

## 简介

创建云游戏服务器









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGameServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUGameCities)获取 |**Yes**|
| **Name** | string | 云游戏服务器实例名称。默认：UPhone。请遵照字段规范设定实例名称。 |**Yes**|
| **ServerModelName** | string | 云游戏服务器规格名称，不超过64个字节。可通过[查询云游戏服务器规格列表]()查询支持的云游戏服务器规格。 |**Yes**|
| **Tag** | string | 业务组。默认：Default（Default即为未分组）。请遵照[字段规范](api/uhost-api/specification)设定业务组。 |No|
| **Bandwidth** | int | 限制带宽 |No|
| **ChargeType** | string | 计费模式。枚举值为： > 年 Year，按年付费； > Month，按月付费； 默认为月付 |No|
| **Quantity** | string | 购买时长。默认值: 1。月付时，此参数传0，代表购买至月末。 |No|
| **CouponId** | string | 云游戏服务器代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看。注：代金券对带宽不适用，仅适用于云游戏服务器计费 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServerId** | string | 云游戏服务器的实例 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGameServer
&ProjectId=fKmztNKW
&Name=wXlgqQEd
&ServerModelName=GZcZlWkg
&CityId=ylylVinA
&ChargeType=TityKMJy
&Quantity=iRacnrnh
&CouponId=HACXlsJo
&Tag=eLqKKBLo
&Bandwidth=3
```

### 响应示例
    
```json
{
  "Action": "CreateUGameServerResponse",
  "Message": "GObrTeXF",
  "RetCode": 0,
  "ServerId": "pliksAcd"
}
```





