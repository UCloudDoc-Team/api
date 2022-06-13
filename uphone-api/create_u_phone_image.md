# 创建云手机镜像 - CreateUPhoneImage

## 简介

创建云手机镜像。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUPhoneImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](https://cms-docs.ucloudadmin.com/api/uphone-api/describe_u_phone_cities)获取 |**Yes**|
| **UPhoneId** | string | 手机实例的资源ID |**Yes**|
| **Name** | string | 镜像名称。长度为2\~128个英文或中文字符。 |No|
| **Description** | string | 镜像的描述信息。长度为2\~256个英文或中文字符 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageId** | string | 云手机自定义镜像资源 ID |No|
| **JobId** | string | 请求的唯一标识Id，`RetCode`为0时返回，可根据此ID查询请求的执行状态 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUPhoneImage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=RStFfKVg
&ImageName=uhfNKUUJ
&Description=BSJwSYwp
&UPhoneId=gLitcBLD
&CityId=EEnwuhCM
&BizType=urTyytBC
```

### 响应示例
    
```json
{
  "Action": "CreateUPhoneImageResponse",
  "ImageId": "CzyvAjwT",
  "JobId": "VsShAPSg",
  "Message": "TVlJWLlr",
  "RetCode": 0
}
```





