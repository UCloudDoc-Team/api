# 列出所有项目 - ListProjects

## 简介

列出所有项目






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListProjects)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListProjects`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Offset** | string |  |No|
| **Limit** | string |  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Projects** | array[[*Project*](#Project)] | 项目信息 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### Project

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectID** | string | 项目ID |**Yes**|
| **ProjectName** | string | 项目名称 |**Yes**|
| **UserCount** | int | 用户数量 |**Yes**|
| **CreatedAt** | int | 创建时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListProjects
&Offset=jNYCtQbd
&Limit=zmvwjdzF
```

### 响应示例
    
```json
{
  "Action": "ListProjectsResponse",
  "Message": "grnIyjqc",
  "Projects": [
    {
      "CreatedAt": 8,
      "ProjectID": "lhxTxRry",
      "ProjectName": "VKDPDmun",
      "UserCount": 7
    }
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





