# 修改云手机名称 - ModifyUPhoneName

## 简介

修改指定云手机实例名称。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyUPhoneName`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **UPhoneId** | string | 云手机实例的资源ID |**Yes**|
| **Name** | string | 云手机实例名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UPhoneId** | string | 云手机实例的资源ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyUPhoneName
&Region=cn-zj
&ProjectId=bjhmgMYR
&UPhoneId=sTYrwZGP
&Name=tyIJXBlQ
&CityId=kfFIYRyY
```

### 响应示例
    
```json
{
  "Action": "ModifyUPhoneNameResponse",
  "Message": "llejkHMO",
  "RetCode": 0,
  "UPhoneId": "TlhqHJpU"
}
```





