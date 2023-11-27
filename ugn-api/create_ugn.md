# 创建云联网 - CreateUGN

## 简介

创建云联网






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGN)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string |  |No|
| **Remark** | string |  |No|
| **Networks.N** | string | 数组，数组内每个元素的字段如下：<br />NetworkID：string，网络实例 ID，如 uvnet-xxxx；<br />Type：string，网络实例类型，枚举值：VPC/HybridGW/...；<br />Region：string，网络实例所属地域，如 cn-sh2；<br />OrgName：string，网络实例所属项目名，如 org-xxx |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGNID** | string |  |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGN
&Region=cn-zj
&Zone=cn-zj-01
&Name=y
&Description=YkZbgQqx
&NetworkID=cKOOwPGM
&VNI=3
&Type=VPC
&RegionID=7
&Name=CBrkRfjs
&Remark=RdoCHKoq
&Name=BOBPZXka
&Remark=ssDwOShx
&ProjectId=topsywLe
```

### 响应示例
    
```json
{
  "Action": "CreateUGNResponse",
  "Message": "rzwvFWVQ",
  "RetCode": 0,
  "UGNID": "ETCQCRsB"
}
```





