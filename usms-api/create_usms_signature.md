# 申请短信签名 - CreateUSMSSignature

## 简介

调用接口CreateUSMSSignature申请短信签名

?> 您可以通过调用接口CreateUSMSSignature或者到控制台申请短信签名，短信签名需符合[UCloud服务协议](https://docs.ucloud.cn/management_monitor/usms/introduction/service_level)，短信签名申请流程可参见官网[短信签名审核规范](https://docs.ucloud.cn/management_monitor/usms/introduction/2005/2103)说明；




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUSMSSignature)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSMSSignature`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **SigType** | int | 签名类型，说明如下：0-公司或企业的全称或简称；1-App应用的全称或简称；2-工信部备案网站的全称或简称；3-公众号或小程序的全称或简称；4-商标名的全称或简称；5-政府/机关事业单位/其他单位的全称或简称； |**Yes**|
| **SigPurpose** | int | 签名用途，0-自用，1-他用； |**Yes**|
| **CertificateType** | int | 签名的资质证明文件类型，需与签名类型保持一致，说明如下：0-三证合一/企业营业执照/组织机构代码证书/社会信用代码证书；1-应用商店后台开发者管理截图；2-备案服务商的备案成功截图(含域名，网站名称，备案号)；3-公众号或小程序的管理界面截图；4-商标注册证书；5-组织机构代码证书、社会信用代码证书； |**Yes**|
| **Description** | string | 短信签名申请原因 |**Yes**|
| **File** | string | 短信签名的资质证明文件，需先进行base64编码格式转换，此处填写转换后的字符串。文件大小不超过4 MB |**Yes**|
| **International** | boolean | 国内/国际短信。true:国际短信，false:国内短信，若不传值则默认该值为false |No|
| **ProxyFile** | string | 短信签名授权委托文件，需先进行base64编码格式转换，此处填写转换后的字符串。文件大小不超过4 MB；当您是代理并使用第三方的签名时（也即SigPurpose为1-他用），该项为必填项； |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SigId** | string | 短信签名ID（短信签名申请时的工单ID） |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSMSSignature
&ProjectId=org-bxxxxy
&SigContent=UCloud
&SigType=0
&SigPurpose=0
&CertificateType=0
&Description=forcompanyused
&File=iVBORw0KGgoXXXXXXXXXXXXXXXXXXNSUhEU
&International=true
```

### 响应示例
    
```json
{
  "Action": "CreateUSMSSignatureResponse",
  "Message": "Rqpugfyt",
  "RetCode": 0,
  "SignatureId": "SIG20190XXX2C1844"
}
```





