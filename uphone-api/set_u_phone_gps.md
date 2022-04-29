# 设置云手机GPS信息 - SetUPhoneGPS

## 简介

设置云手机GPS信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SetUPhoneGPS`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **UPhoneGPSs.N.UPhoneId** | string | 云手机ID |No|
| **UPhoneGPSs.N.Longitude** | float | 经度：-180\~180 |No|
| **UPhoneGPSs.N.Latitude** | float | 纬度：-90\~90 |No|
| **UPhoneGPSs.N.Altitude** | float | 海拔 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 请求的唯一标识Id，`RetCode`为0时返回，可根据此ID查询请求的执行状态 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SetUPhoneGPS
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=vugJqbBA
&UPhoneGPS=eUxBxLZr
&UPhoneGPSs.N.Longitude=9.57266
&UPhoneGPSs.N.Latitude=8.24851
&UPhoneGPSs.N.Altitude=6.12783
&CityId=QlYovAFx
```

### 响应示例
    
```json
{
  "Action": "SetUPhoneGPSResponse",
  "JobId": "zZjdUFMH",
  "RetCode": 0,
  "UPhoneGPS": [
    {
      "Altitude": 9.49688,
      "Latitude": 45,
      "Longitude": 90
    }
  ]
}
```





