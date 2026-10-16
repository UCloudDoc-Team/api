# 查询联系人 - ListApplicantContact

## 简介

查询联系人









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListApplicantContact`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 查询到的数量 |**Yes**|
| **ContactSet** | array[[*ApplicantContact*](#ApplicantContact)] | 联系人列表 |**Yes**|

#### 数据模型


#### ApplicantContact

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ContactID** | int | 联系人id |**Yes**|
| **ContactName** | string | 姓名 |**Yes**|
| **ContactPhone** | string | 电话 |**Yes**|
| **ContactEmail** | string | 邮件 |**Yes**|
| **ContactAddress** | string | 联系地址 |**Yes**|
| **ContactPostalCode** | string | 邮编 |**Yes**|
| **ContactTitle** | string | 职位 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListApplicantContact
&TopOrganizationID=323423
```

### 响应示例
    
```json
{
  "Action": "ListApplicantContactResponse",
  "ContactSet": [
    {
      "ContactAddress": "",
      "ContactEmail": "",
      "ContactID": "",
      "ContactName": "",
      "ContactPhone": "",
      "ContactPostalCode": "",
      "ContactTitle": ""
    },
    {
      "ContactAddress": "",
      "ContactEmail": "",
      "ContactID": "",
      "ContactName": "",
      "ContactPhone": "",
      "ContactPostalCode": "",
      "ContactTitle": ""
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





