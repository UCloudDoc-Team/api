# 查询模板状态信息 - QueryISMSTemplate

## 简介

查询模板状态信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryISMSTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TemplateId** | string | 模板Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*OutTemplate*](#OutTemplate) | 模板状态信息 |**Yes**|
| **ReqUuid** | string | 本次请求uuid |No|

#### 数据模型


#### OutTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateId** | string | 模板ID |No|
| **Purpose** | int | 视频短信类型（3-会员营销） |No|
| **TemplateName** | string | 模板名称 |No|
| **Remark** | string | 备注信息 |No|
| **CreateTime** | int | 创建时间，时间戳格式1629357838 |No|
| **ExpireTime** | int | 截止有效时间，时间戳格式1629357838 |No|
| **StatusDesc** | string | 状态描述。json格式，给出运营商维度的审核状态信息，示例：{"telecom_status":2,"telecom_desc":"审核通过","unicom_status":2,"unicom_desc":"审核通过","mobile_status":2,"mobile_desc":"审核通过"} |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryISMSTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=UuljywiO
&Page=4
&NumPerPage=9
&OrderBy=moRBaKSS
&OrderType=bCBNcume
&FuzzySearch=exfjwYiC
&TemplateIdSet.N=HgHtjluh
```

### 响应示例
    
```json
{
  "Action": "QueryISMSTemplateResponse",
  "Data": [
    {
      "Content": "tcfblONK",
      "CreateTime": 4,
      "ExpireTime": 8,
      "MsgSignature": "ehVSZXkB",
      "MsgTitle": "XxMVCLTB",
      "Purpose": 4,
      "Remark": "vdpsgFOD",
      "ReviewEndTime": 2,
      "ReviewStartTime": 4,
      "StatusDesc": "hDdjpPxy",
      "TemplateId": "OJmcWyJc",
      "TemplateName": "fazHSRkp",
      "UpdateTime": 1
    }
  ],
  "Message": "bDftqkTB",
  "ReqUuid": "rtzkheuj",
  "RetCode": 0,
  "Total": 3
}
```





