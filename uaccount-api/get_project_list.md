# 获取帐号下的项目列表 - GetProjectList

## 简介

获取项目列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetProjectList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetProjectList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IsFinance** | string | 是否是财务账号（Yes：是，No：否） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ProjectCount** | int | 项目总数 |**Yes**|
| **ProjectSet** | array[[*ProjectListInfo*](#ProjectListInfo)] | JSON格式的项目列表实例 |**Yes**|

#### 数据模型


#### ProjectListInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **ProjectName** | string | 项目名称 |**Yes**|
| **CreateTime** | int | 创建时间(Unix时间戳) |**Yes**|
| **IsDefault** | boolean | 是否为默认项目 |**Yes**|
| **ResourceCount** | int | 项目下资源数量（已废弃，不建议使用） |**Yes**|
| **MemberCount** | int | 项目下成员数量 |**Yes**|
| **ParentId** | string | 父项目ID（已废弃） |No|
| **ParentName** | string | 父项目名称（已废弃） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetProjectList
```

### 响应示例
    
```json
{
  "Action": "GetProjectListResponse",
  "ProjectCount": 2,
  "ProjectSet": [
    {
      "CreateTime": 1342434682,
      "IsDefault": true,
      "MemberCount": 1,
      "ProjectId": "org-1",
      "ProjectName": "ucloud",
      "ResourceCount": 52
    },
    {
      "CreateTime": 1468225814,
      "IsDefault": false,
      "MemberCount": 0,
      "ProjectId": "org-2",
      "ProjectName": "test",
      "ResourceCount": 10
    }
  ],
  "RetCode": 0
}
```





