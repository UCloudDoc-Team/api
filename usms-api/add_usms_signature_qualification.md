# 添加短信签名资质申请记录 - AddUSMSSignatureQualification

## 简介

添加短信签名资质申请记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddUSMSSignatureQualification)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUSMSSignatureQualification`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 资质名称 |**Yes**|
| **Attr** | int | 资质属性，0-自用 1-他用 |**Yes**|
| **Status** | int | 状态：0-草稿，1-提交审核 |**Yes**|
| **CompanyName** | string | 公司名称，长度限制100 |No|
| **CompanyCreditCode** | string | 公司统一社会信用代码 |No|
| **CompanyCertificateFileId** | string | 公司证件文件FileId |No|
| **CompanyWorkScenePhotosFileId** | string | 公司工作现场照片FileId |No|
| **HandlerName** | string | 经办人姓名 |No|
| **HandlerIDNumber** | string | 经办人身份证号码 |No|
| **HandlerIDCardFrontImageFileId** | string | 经办人身份证人像面图片FileId |No|
| **HandlerIDCardBackImageFileId** | string | 经办人身份证国徽面图片FileId |No|
| **HandlerHandHeldImageFileId** | string | 经办人手持身份证图片FileId |No|
| **ManagerName** | string | 法人姓名 |No|
| **ManagerIDNumber** | string | 法人身份证号码 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **QualificationId** | string | 资质Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUSMSSignatureQualification
&ProjectId=kKNmmeMB
&Name=koNRhZtW
&Attr=4
&Status=4
&CompanyName=AedSnHhH
&CompanyCreditCode=GrCJWHiI
&CompanyCertificateFile=rZCjRLUy
&CompanyWorkScenePhotos=zwMbEMjS
&HandlerName=nfWBwgvo
&HandlerIDNumber=jCnyLEkF
&HandlerIDCardFrontImage=JfiOIOwa
&HandlerIDCardBackImage=YzJtUGtk
&HandlerHandHeldImage=hrYNUUWv
&PowerOfAttorney=CfKkfNRw
&ManagerName=qJLyZyuJ
&ManagerIDNumber=PmDPyumA
&CompanyCertificateFileId=jzabnZgb
&CompanyWorkScenePhotosFileId=cHpspiLG
&HandlerIDCardFrontImageFileId=cqvWwPbw
&HandlerIDCardBackImageFileId=kKXaojft
&HandlerHandHeldImageFileId=IRSHOfWA
&PowerOfAttorneyFileId=FXGYjKwb
```

### 响应示例
    
```json
{
  "Action": "AddUSMSSignatureQualificationResponse",
  "Message": "wEEENDbT",
  "QualificationId": "RzLxKRaF",
  "RetCode": 0
}
```





