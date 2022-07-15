# 重置云手机 - ResetUPhone

## 简介

将云手机恢复为创建时的状态。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResetUPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **UPhoneIds.N** | string | 【数组】云手机实例的资源 ID，调用方式举例：UPhoneIds.0=希望重置的云手机实例 1 的 UPhoneId，UPhoneIds.1=云手机实例 2 的 UPhoneId。 |**Yes**|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|
| **ImageId** | string | 镜像ID，默认为空。不为空则手机会以填写的镜像进行重置，为空则手机会以重置前的镜像重置 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 异步请求成功后返回JobId，用以查询Job状态 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResetUPhone
&Region=cn-zj
&ProjectId=uZfEyfkI
&UPhoneIds.N=zwZrpkCk
&CityId=xFXLvbhZ
&BizType=EFBDFdpb
&ImageId=Otmxpqph
&UPhoneModelName=FIbzXsnS
&MediaBandwidth=BqYadJEW
```

### 响应示例
    
```json
{
  "Action": "ResetUPhoneResponse",
  "JobId": "UKcWGJzX",
  "Message": "ouRAdBqe",
  "RetCode": 0
}
```





