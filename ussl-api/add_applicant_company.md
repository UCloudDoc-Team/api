# 添加公司信息 - AddApplicantCompany

## 简介

添加公司信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddApplicantCompany`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CompanyName** | string | 名称 |**Yes**|
| **CompanyCountry** | string | 国家码 |**Yes**|
| **CompanyRegion** | string | 省 |No|
| **CompanyCity** | string | 城市 |No|
| **CompanyAddress** | string | 详细地址 |No|
| **CompanyPhone** | string | 联系电话 |No|
| **CompanyPostalCode** | string | 邮编 |No|
| **CompanyDivision** | string | 部门 |No|
| **CompanyType** | string | 机构性质 |No|
| **CompanyCodeType** | string | 机构码类型 |No|
| **CompanyCode** | string | 机构代码 |No|
| **CompanyID** | int | 公司ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddApplicantCompany
&ProjectId=MQofTlvs
&Region=XbPFWarL
&Name=MYZwEYMw
&Country=fwvBNYIK
&City=wYNfVlJq
&Address=QVuXfszC
&Phone=BCqDzeTk
&PostalCode=RwmAdwCQ
&Division=aVnGkyMo
&CompanyType=ZeWdsxav
&CompanyCodeType=AgKAUBdF
&CompanyCode=tNnhOjRi
&CompanyType=TxPJKAhW
&CompanyCodeType=RSsGBOvx
&CompanyCode=rheCvKzn
&CompanyID=mKkjmfxo
```

### 响应示例
    
```json
{
  "Action": "AddApplicantCompanyResponse",
  "RetCode": 0
}
```





