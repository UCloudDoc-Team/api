# 设置UDisk数据方舟的状态 - SetUDiskUDataArkMode

## 简介

设置UDisk数据方舟的状态

?> "17090": "开启或关闭方舟失败，请稍后再试。"<br />"17091": "该磁盘距离关闭数据方舟不足三天，无法再次开启"




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SetUDiskUDataArkMode)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SetUDiskUDataArkMode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **UDiskId** | string | 需要设置数据方舟的UDisk的Id |**Yes**|
| **UDataArkMode** | string | 【即将废弃，开启快照服务时，免费开启数据方舟】是否开启数据方舟。Yes：开启，No：不开启，默认值：No |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SetUDiskUDataArkMode
&Region=cn-sh2
&Zone=cn-sh2-01
&UDiskId=bs-xxx
&UDiskUDataArkMode=Yes
&CouponId=kdnbYyBF
```

### 响应示例
    
```json
{
  "Action": "SetUDiskUDataArkModeResponse",
  "RetCode": 0
}
```





