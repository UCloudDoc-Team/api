# 获取地域和可用区列表 - GetRegion

## 简介

获取用户在各数据中心的权限等信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetRegion)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetRegion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Regions** | array[[*RegionInfo*](#RegionInfo)] | 各数据中心信息 |No|

#### 数据模型


#### RegionInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RegionId** | int | 数据中心ID |**Yes**|
| **RegionName** | string | 数据中心名称 |**Yes**|
| **IsDefault** | boolean | 是否用户当前默认数据中心 |**Yes**|
| **BitMaps** | string | 用户在此数据中心的权限位 |**Yes**|
| **Region** | string | 地域名字，如cn-bj |**Yes**|
| **Zone** | string | 可用区名字，如cn-bj-01 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetRegion
```

### 响应示例
    
```json
{
  "Action": "GetRegionResponse",
  "RetCode": 0
}
```





