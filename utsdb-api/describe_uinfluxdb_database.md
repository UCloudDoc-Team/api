# 描述UInfluxdb数据库 - DescribeUInfluxdbDatabase

## 简介

描述UInfluxdb数据库






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUInfluxdbDatabase)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUInfluxdbDatabase`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UInfluxdbId** | string |  |**Yes**|
| **Offset** | int |  |No|
| **Limit** | int |  |No|
| **DatabaseName** | string |  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DatabaseInfo** | array[[*DatabaseInfo*](#DatabaseInfo)] |  |**Yes**|

#### 数据模型


#### DatabaseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DatabaseName** | string | 数据库名 |No|
| **State** | string | 数据库状态 |No|
| **Description** | string | 数据库描述 |No|
| **RetentionPolicy** | string | 保留策略 |No|
| **AccountInfo** | array[[*AccountInfo*](#AccountInfo)] | 账户信息 |No|

#### AccountInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Account** | string | 账户名 |No|
| **Privilege** | string | 权限 |No|
| **Password** | string | 密码 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUInfluxdbDatabase
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=hYHEdkPl
&UInfluxdbId=IVwHikVw
&Limit=3
&DatabaseName=GMCNJiLM
&Offset=7
```

### 响应示例
    
```json
{
  "Action": "DescribeUInfluxdbDatabaseResponse",
  "DatabaseInfo": [
    {
      "AccountInfo": [
        {
          "Amount": "CQBtFslG",
          "AmountAvailable": "UeVaUXpf",
          "AmountCredit": "TdCnAGBu",
          "AmountFree": "ZohaYdZJ",
          "AmountFreeze": 3.88429
        }
      ],
      "DatabaseName": "pIkgZgWV",
      "Description": "pAwfiVoh",
      "State": "BtUeTxif"
    }
  ],
  "RetCode": 0
}
```





