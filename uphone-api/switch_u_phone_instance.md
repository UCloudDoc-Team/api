# 故障更换云手机 - SwitchUPhoneInstance

## 简介

故障更换云手机









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SwitchUPhoneInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](https://cms-docs.ucloudadmin.com/api/uphone-api/describe_u_phone_cities)获取 |**Yes**|
| **SwitchInfos.N.UPhoneId** | string | 【数组】云手机实例的资源 ID，N<200 |**Yes**|
| **SwitchInfos.N.ImageId** | string | 【数组】云手机实例的镜像ID，N<200，该值为空时，默认使用云手机之前的镜像ID，如果镜像ID已经不存在了则会返回错误 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 任务ID，用来查询故障更换云手机任务状态 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SwitchUPhoneInstance
&ProjectId=VeFtsXGE
&CityId=IVBWnjzV
&ReplaceInfos.N.UPhoneId=wvkdTqOX
&ReplaceInfos.N.ImageId=wQmrwvcg
```

### 响应示例
    
```json
{
  "Action": "SwitchUPhoneInstanceResponse",
  "JobId": "puwVkUon",
  "Message": "AXpSleAe",
  "RetCode": 0
}
```





