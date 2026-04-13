# 获取团队列表 - ListCompShareTeam

## 简介

获取团队列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCompShareTeam`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Teams** | array[[*CompShareTeamInfo*](#CompShareTeamInfo)] | 团队信息数组 |No|

#### 数据模型


#### CompShareTeamInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | 团队Id |No|
| **Name** | string | 团队名称 |No|
| **CompanyId** | int | 管理者公司Id |No|
| **Description** | string | 团队简介 |No|
| **MemberCount** | int | 成员数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCompShareTeam
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=FEgwcpDn
```

### 响应示例
    
```json
{
  "Action": "ListCompShareTeamResponse",
  "RetCode": 0,
  "Teams": [
    {
      "CompanyId": 5,
      "Description": "zbjRAoHG",
      "Id": 2,
      "MemberCount": 3,
      "Name": "lKIVptPV"
    }
  ]
}
```





