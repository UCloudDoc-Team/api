# 获取配额信息 - GetUFileQuotaInfo

## 简介

获取配额信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileQuotaInfo)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileQuotaInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **QuotaType.N** | string | 配额类型，取值为storage-volume, download-traffic或request-count |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileQuotaDataSetItem*](#UFileQuotaDataSetItem)] | 配额信息数据集 |No|

#### 数据模型


#### UFileQuotaDataSetItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 可用地域 |No|
| **Owe** | int | 是否欠费：1表示欠费；0表示未欠费 |No|
| **Storage** | [*UFileQuotaLeft*](#UFileQuotaLeft) | 剩余存储容量 |No|
| **DownloadFlow** | [*UFileQuotaLeft*](#UFileQuotaLeft) | 剩余下载流量 |No|
| **RequestCnt** | [*UFileQuotaLeft*](#UFileQuotaLeft) | 剩余请求次数 |No|

#### UFileQuotaLeft

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Left** | float | 配额剩余量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileQuotaInfo
&Region=cn-bj2
&QuotaType.0=storage-volume
&QuotaType.1=download-traffic
&QuotaType.2=request-count
&ProjectId=org-xxx
```

### 响应示例
    
```json
{
  "Action": "GetUFileQuotaInfoResponse",
  "DataSet": [
    {
      "DownloadFlow": {
        "Left": -5.1803
      },
      "Owe": 1,
      "Region": "cn-bj",
      "RequestCnt": {
        "Left": 202
      },
      "Storage": {
        "Left": -13507.2
      }
    }
  ],
  "RetCode": 0
}
```





