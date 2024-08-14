# 创建域名记录 - CreateUDNSRecord

## 简介

创建域名记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDNSRecord)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDNSRecord`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DNSZoneId** | string | 域名资源ID |**Yes**|
| **Name** | string | 主机记录 |**Yes**|
| **Type** | string | 记录类型。枚举值，“A”,"CNAME","MX","AAAA","SRV","PTR","TXT"。 |**Yes**|
| **Value** | string | 数值组，支持逗号分割。格式为：Value\|权重\|IsEnabled，其中权重支持1-10，IsEnabled为枚举值（1为启用，0为禁用）。输入格式示例：192.168.1.1\|1\|1,192.168.1.2\|10\|0。 |**Yes**|
| **ValueType** | string | 值类型。枚举值，“Normal”，标准；“Multivalue”，多值返回。仅在值为“Multivalue”时，Value的权重生效。 |**Yes**|
| **TTL** | int | TTL值，范围为5-600，单位为秒。默认为5 |No|
| **Remark** | string | 记录的备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DNSRecordId** | string | 域名记录的资源ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDNSRecord
&Region=cn-zj
&ProjectId=GgGuwDzg
&DNSZoneId=OuEgFBYW
&Name=NJBwCHTv
&Type=yLvrhvaV
&Value=sDfoIsxo
&ValueType=DTSxqfSx
&TTL=7
&Remark=snXvcBYa
```

### 响应示例
    
```json
{
  "Action": "CreateUDNSRecordResponse",
  "RecordId": "vqoWymst",
  "RetCode": 0
}
```





