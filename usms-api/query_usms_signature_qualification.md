# 获取短信签名资质申请记录详情 - QueryUSMSSignatureQualification

## 简介

获取短信签名资质申请记录详情






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryUSMSSignatureQualification)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryUSMSSignatureQualification`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **QualificationId** | string | 签名资质Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*OutSignatureQualificationDetail*](#OutSignatureQualificationDetail) | 签名资质详细信息 |**Yes**|

#### 数据模型


#### OutSignatureQualificationDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **QualificationId** | string | 资质Id |No|
| **Name** | string | 资质名称 |No|
| **Attr** | int | 资质属性：0-自用，1-他用 |No|
| **CompanyName** | string | 公司名称 |No|
| **CompanyCreditCode** | string | 统一社会信用代码 |No|
| **CompanyCertificateFile** | string | 公司证件文件链接 |No|
| **ManagerName** | string | 负责人姓名 |No|
| **ManagerIDNumber** | string | 负责人证件号码 |No|
| **HandlerName** | string | 经办人姓名 |No|
| **HandlerIDNumber** | string | 经办人证件号码 |No|
| **HandlerIDCardFrontImage** | string | 经办人身份证人像面图片链接 |No|
| **HandlerIDCardBackImage** | string | 经办人身份证国徽面图片链接 |No|
| **HandlerHandHeldImage** | string | 经办人手持身份证图片链接 |No|
| **CompanyWorkScenePhotos** | string | 工作现场照片链接 |No|
| **PowerOfAttorney** | string | 授权委托书文件链接 |No|
| **Status** | int | 状态:0-草稿 1-审核中 2-审核通过 3-审核未通过 4-人工禁用 |No|
| **ErrCode** | int | 审核未通过错误码 |No|
| **ErrDesc** | string | 审核未通过错误原因 |No|
| **CreateTime** | int | 创建时间戳 |No|
| **ModifyTime** | int | 修改时间戳 |No|
| **ReviewStartTime** | int | 审核开始时间戳 |No|
| **ReviewEndTime** | int | 审核完成时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryUSMSSignatureQualification
&ProjectId=IUzoimjy
&QualificationId=jXoTeWoN
```

### 响应示例
    
```json
{
  "Action": "QueryUSMSSignatureQualificationResponse",
  "Data": {},
  "Message": "GRrYyBYw",
  "RetCode": 0
}
```





