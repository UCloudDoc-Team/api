# 获取团队详细信息 - GetCompShareTeamInfo

## 简介

获取团队详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCompShareTeamInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TeamId** | int | 团队Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Team** | [*CompShareTeamDetailInfo*](#CompShareTeamDetailInfo) | 团队信息 |No|
| **TeamRelation** | array[[*TeamRelation*](#TeamRelation)] | 团队关系数组 |No|

#### 数据模型


#### CompShareTeamDetailInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | 团队Id |No|
| **Name** | string | 团队名称 |No|
| **CompanyId** | int | 管理者公司Id |No|
| **Description** | string | 团队简介 |No|
| **Deleted** | int | 删除状态 0: 未删除 1: 已删除 |No|

#### TeamRelation

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TeamId** | int | 团队ID |No|
| **TeamName** | string | 团队名称 |No|
| **UserCompanyId** | int | 成员公司Id |No|
| **VirtualCompanyId** | int | 虚拟账号公司Id |No|
| **Status** | string | 邀请状态：Pending（待同意）、Joined（已加入）、Rejected（拒绝）、Canceled（取消） |No|
| **RemarkName** | string | 备注名称 |No|
| **CreateTime** | int | 邀请时间 |No|
| **AllocateAmount** | int | 已分配金额 |No|
| **AvailableAmount** | int | 余额 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCompShareTeamInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=KEQDCtyR
&TeamId=8
```

### 响应示例
    
```json
{
  "Action": "GetCompShareTeamInfoResponse",
  "Message": "WaJthEgk",
  "RetCode": 0,
  "Team": {},
  "TeamRelation": [
    {
      "AllocateAmount": 1,
      "AvailableAmount": 1,
      "CreateTime": 7,
      "RemarkName": "LqisMSvE",
      "Status": "LuMsOhiH",
      "TeamId": 8,
      "TeamName": "LGmOlTxm",
      "UserCompanyId": 3,
      "VirtualCompanyId": 7
    }
  ]
}
```





