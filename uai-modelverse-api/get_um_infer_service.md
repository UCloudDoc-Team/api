# 获取模型服务 - GetUMInferService

## 简介

获取模型服务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMInferService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UminferID** | string | 推理服务id |No|
| **Offset** | string | offset |No|
| **Limit** | string | limit |No|
| **UminferType** | string | private: 私有部署；<br />preDeploy: 预置模型/体验中心。<br />使用 ',' 英文逗号分隔的字符串，默认 private |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*UMInferServiceData*](#UMInferServiceData)] | 推理服务数据 |**Yes**|
| **TotalCount** | int | 模型数量 |No|

#### 数据模型


#### UMInferServiceData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Replicas** | int | 副本数 |No|
| **ReadyReplicas** | int | 实际启动的副本数 |No|
| **ComputingUnit** | int | 算力单元 |No|
| **UminferID** | string | 推理服务资源id |No|
| **UminferType** | string | 推理服务资源类型 |No|
| **Status** | string | 服务状态 |No|
| **URL** | string | 服务的url |No|
| **Name** | string | 服务名字 |No|
| **CreateTime** | int | 创建时间 |No|
| **ModelID** | string | 模型id |No|
| **ModelName** | string | 模型名字 |No|
| **Describe** | string | 描述 |No|
| **Key** | string | 模型认证key |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMInferService
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=GNVYddTa
&UminferID=RsxHEWlY
&Offset=LXFRVNPf
&Limit=vMvKDwux
&UminferType=ePdgTiBX
&UminferType=iElIyEEt
```

### 响应示例
    
```json
{
  "Action": "GetUMInferServiceResponse",
  "Data": [
    {
      "CreateTime": 2,
      "Describe": "UIMSNZYA",
      "Key": "kvIMoROs",
      "ModelID": "upulyoUb",
      "ModelName": "mwqyUBRb",
      "Name": "pqXdTEHZ",
      "Status": "cn-zj",
      "URL": "VNUrGwuD",
      "UminferID": "KRuoTTwF"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





