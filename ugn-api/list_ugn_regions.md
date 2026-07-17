# 获取UGN可加入地域 - ListUGNRegions

## 简介

获取UGN的可加入地域列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUGNRegions)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUGNRegions`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SelectedRegions.N** | string | 数组，已选区域，例如：cn-bj2， cn-wlcb |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RegionLIst** | array[[*UgnRegion*](#UgnRegion)] | 可加入地域列表 |**Yes**|

#### 数据模型


#### UgnRegion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域名称 |**Yes**|
| **RegIonId** | string | 地域ID |**Yes**|
| **IsOverseas** | boolean | 是否为海外地域 |**Yes**|
| **IsOnline** | boolean | 是否上线 |**Yes**|
| **Needs** | array[string] | 添加region需要做的校验 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUGNRegions
&SelectedRegions.N=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "ListUGNRegionsResponse",
  "Message": "ok",
  "RegionList": [
    {
      "IsOnline": true,
      "IsOverseas": false,
      "Needs": [],
      "Region": "cn-bj2",
      "RegionId": "1000001"
    },
    {
      "IsOnline": true,
      "IsOverseas": false,
      "Needs": [],
      "Region": "cn-sh2",
      "RegionId": "1000009"
    }
  ],
  "RetCode": 0
}
```





