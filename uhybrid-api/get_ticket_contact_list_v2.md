# 获取工单联系人 - GetTicketContactListV2

## 简介

获取工单联系人






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetTicketContactListV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetTicketContactListV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ContactType** | int | 联系人类型，枚举值为： <br /><br /> > 1，创建工单共有的联系人信息； <br /><br /> > 2，人员入室特有的联系人信息； |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ContactList** | array[[*TicketContact*](#TicketContact)] | 联系人数组 |No|

#### 数据模型


#### TicketContact

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | id |No|
| **Flag** | int | 联系人类型：1 - 创建工单共有的联系人信息 2 - 人员入室特有的联系人信息 |No|
| **CompanyId** | int | 公司id |No|
| **AccountId** | int | 项目id |No|
| **RegionId** | int | 区域 |No|
| **ZoneId** | int | 可用区 |No|
| **Name** | string | 姓名 |No|
| **Email** | string | 邮箱 |No|
| **Phone** | string | 电话 |No|
| **IdentityCard** | string | 身份证号 |No|
| **CompanyName** | string | 联系人所属公司 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetTicketContactListV2
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=CVgilqKo
&ContactType=1
```

### 响应示例
    
```json
{
  "Action": "GetTicketContactListV2Response",
  "ContactList": [
    {
      "AccountId": 7,
      "CompanyId": 2,
      "CompanyName": "eJskeYFD",
      "Email": "sdgiVRwo",
      "Id": "fQCZraOg",
      "IdentityCard": "hVlZiTzw",
      "Name": "iCPgfsxz",
      "Phone": "jNaHDqXl",
      "RegionId": 6,
      "ZoneId": 2
    }
  ],
  "RetCode": 0
}
```





