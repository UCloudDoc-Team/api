# 云游戏入队 - RegisterUGameQueue

## 简介

云游戏入队









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RegisterUGameQueue`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 |**Yes**|
| **AppVersionId** | string | 应用版本的唯一标识ID。 |**Yes**|
| **UserId** | string | 客户端用户 ID。 |**Yes**|
| **CityIds.N** | string | 【数组】城市Id，通过[获取城市列表](#DescribeCities)获取；调用方式举例：CityIds.0=city_1，CityIds.0=city_2 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RegisterUGameQueue
&ProjectId=RkVTqexr
&AppVersionId=FgPiaTYH
&UserId=FjrMhMOQ
&CityIds.N=dKaNfugV
```

### 响应示例
    
```json
{
  "Action": "RegisterUGameQueueResponse",
  "Message": "pkXalHHP",
  "RetCode": 0
}
```





