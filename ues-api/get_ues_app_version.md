# 获取服务应用版本列表 - GetUESAppVersion

## 简介

获取服务应用版本列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUESAppVersion)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUESAppVersion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 服务应用版本个数 |**Yes**|
| **AppVersionList** | array[[*AppVersion*](#AppVersion)] | 服务应用版本列表 |**Yes**|

#### 数据模型


#### AppVersion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 应用名称，默认值为elasticsearch |**Yes**|
| **AppVersion** | string | 应用版本号 |**Yes**|
| **IsMultiZone** | boolean | 是否支持多区部署，默认为false |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUESAppVersion
&Region=cn-zj
&Zone=cn-zj-01
&AppName=pMcpWDVJ
&ServiceType=TEXBCSel
```

### 响应示例
    
```json
{
  "Action": "GetUESAppVersionResponse",
  "Message": "uraUHQwv",
  "RetCode": 0,
  "TotalCount": 3,
  "UESAppVersionList": [
    {
      "AppName": "zAlzqxAH",
      "AppPort": "IxFzmOON",
      "AppState": "0",
      "AppVersion": "NHtmFBac",
      "ServiceType": "RdRyjiIC"
    },
    {
      "AppName": "QwszIdNN",
      "AppPort": "GiSdUmIU",
      "AppState": "0",
      "AppVersion": "QHtoMnlg",
      "ServiceType": "qdkiCGkh"
    }
  ]
}
```





