# 创建视频短信模板 - CreateISMSTemplate

## 简介

申请视频短信模板









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateISMSTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **MsgTitle** | string | 视频短信标题 |**Yes**|
| **MsgSignature** | string | 视频短信签名 |**Yes**|
| **TemplateName** | string | 视频短信模板名称 |**Yes**|
| **Content** | string | 视频短信模板内容。json数组的字符串格式。如：<br />[<br />{name:"0.txt",type:"txt",content:"北京是一座美丽的城市，我爱北京！",index:0},<br />{name:"1.jpg",type:"jpg",content:"jpg文件字节的base64编码字符串",index:1},{name:”2.mp4”,type:"mp4",content:"mp4文件字节的base64编码字符串",index:2}<br />]。<br />name: 文件名，name中不能出现中文，必须要带上和type相同的后缀；type:文件类型，不能为空，文本为txt，图片为jpg、gif或png，音频为mp3，视频为mp4；content：文件内容，由文本、图片、音频、视频组成，文本使用txt文件，图片使用 jpg、gif、png 格式，音频使用 mp3 格式，视频使用mp4（视频只允许一个），文本、图片、音频、视频文件合计大小不可超过2M；index: 在视频短信中的位置。从0开始。 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **UnsubscribeInfo** | string | 退订信息，如：“回T退订” |**Yes**|
| **Purpose** | int | 模板用途类型：1-验证码类短信模板；2-系统通知类短信模板；3-会员推广类短信模板； |No|
| **NetworkOperator** | string | 需要报备的运营商。json数组的字符串格式。true-需要报备，false-不需要报备。如：{"telecom":true, "mobile":false, "unicom":true } |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 本次接口调用请求Id，用于问题排查。 |**Yes**|
| **TemplateId** | string | 申请的模板Id。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateISMSTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=nuIBGbIN
&MsgTitle=uVNyRtkD
&SignatureId=PyTObdGS
&TemplateName=GFllvblB
&Content=WbjNkdAt
&NetworkOperator=SlCGQIcc
&Remark=pRKRGfxW
&UnsubscribeInfo=cNmRLinz
&Purpose=9
&Purpose=5
```

### 响应示例
    
```json
{
  "Action": "CreateISMSTemplateResponse",
  "Message": "qNIEYKNI",
  "ReqUuid": "BSsrXoNG",
  "RetCode": 0,
  "TemplateId": "fnxUcKEd"
}
```





