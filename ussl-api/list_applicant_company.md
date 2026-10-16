# 个人中心查询公司列表 - ListApplicantCompany

## 简介

个人中心查询公司列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListApplicantCompany`                        | **Yes** |
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
| **TotalCount** | int | 总数量 |**Yes**|
| **CompanySet** | array[[*ApplicantCompany*](#ApplicantCompany)] | 公司列表 |**Yes**|

#### 数据模型


#### ApplicantCompany

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CompanyRegion** | string | 省 |**Yes**|
| **CompanyID** | int | 公司ID |**Yes**|
| **CompanyName** | string | 公司名称 |**Yes**|
| **CompanyCountry** | string | 国家码 |**Yes**|
| **CompanyCity** | string | 城市 |**Yes**|
| **CompanyAddress** | string | 详细地址 |**Yes**|
| **CompanyPhone** | string | 电话 |**Yes**|
| **CompanyPostalCode** | string | 邮编 |**Yes**|
| **CompanyDivision** | string | 部门 |**Yes**|
| **CompanyCode** | string | 公司编号 |**Yes**|
| **CompanyCodeType** | string | 公司编号类型 |**Yes**|
| **CompanyType** | string | 公司类型 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListApplicantCompany
&TopOrganizationID=56543
```

### 响应示例
    
```json
{
  "Action": "ListApplicantCompanyResponse",
  "CompanySet": [
    {
      "CompanyAddress": "",
      "CompanyCity": "",
      "CompanyCode": "",
      "CompanyCodeType": "",
      "CompanyCountry": "",
      "CompanyDivision": "",
      "CompanyID": "",
      "CompanyName": "",
      "CompanyPhone": "",
      "CompanyPostalCode": "",
      "CompanyRegion": "",
      "CompanyType": ""
    },
    {
      "CompanyAddress": "",
      "CompanyCity": "",
      "CompanyCode": "",
      "CompanyCodeType": "",
      "CompanyCountry": "",
      "CompanyDivision": "",
      "CompanyID": "",
      "CompanyName": "",
      "CompanyPhone": "",
      "CompanyPostalCode": "",
      "CompanyRegion": "",
      "CompanyType": ""
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





