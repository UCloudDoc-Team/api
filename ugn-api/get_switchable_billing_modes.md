# 获取带宽包可以切换的计费类型 - GetSwitchableBillingModes

## 简介

获取带宽包可以切换的计费类型






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSwitchableBillingModes)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSwitchableBillingModes`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **BwPackageID** | string | 带宽包 id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PayModes** | array[string] | 支持的计费类型。FixedBw：固定带宽，Traffic：流量计费，Max5：第五峰值。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSwitchableBillingModes
&ProjectId=org-1jzytw
&BwPackageID=bw-1geqomps8b4x
```

### 响应示例
    
```json
{
  "Action": "GetSwitchableBillingModesResponse",
  "Message": "ok",
  "PayModes": [
    "Max5"
  ],
  "RetCode": 0
}
```





