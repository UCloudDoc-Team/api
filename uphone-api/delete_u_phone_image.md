# 删除自制云手机镜像。 - DeleteUPhoneImage

## 简介

删除自制云手机镜像。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteUPhoneImage`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageId** | string | 云手机自定义镜像资源ID |**Yes**|
| **ProductType** | string | 枚举值【必填项】。表示当前操作的产品类型，目前固定值【uphone】，表示云手机场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageId** | string | 云手机自定义镜像资源ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteUPhoneImage
&Region=cn-zj
&ProjectId=KzjmAvLp
&ImageId=WMGIEjnC
&ImageName=nWscxGak
&Description=OTaCzNxo
&ProductType=kGorfhbM
&ProductType=eOmLfgJT
```

### 响应示例
    
```json
{
  "Action": "DeleteUPhoneImageResponse",
  "ImageId": "PwXiVADP",
  "Message": "bVRgbsvn",
  "RetCode": 0
}
```





