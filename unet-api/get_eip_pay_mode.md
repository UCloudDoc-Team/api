# 获取弹性IP计费方式 - GetEIPPayMode

## 简介

获取弹性IP计费模式






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetEIPPayMode)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetEIPPayMode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **EIPId.N** | string | 弹性IP的资源Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **EIPPayMode** | array[[*EIPPayModeSet*](#EIPPayModeSet)] | EIP的计费模式, 参见 EIPPayModeSet |No|

#### 数据模型


#### EIPPayModeSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIPId** | string | EIP的资源ID |No|
| **EIPPayMode** | string | EIP的计费模式. 枚举值为：Bandwidth, 带宽计费;Traffic, 流量计费; "ShareBandwidth",共享带宽模式 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetEIPPayMode
&Region=cn-bj2
&EIPId=eip-eij2r4
```

### 响应示例
    
```json
{
  "Action": "GetEIPPayModeResponse",
  "EIPPayMode": [
    {
      "EIPId": "eip-eij2r4",
      "EIPPayMode": "Traffic"
    }
  ],
  "RetCode": 0
}
```





