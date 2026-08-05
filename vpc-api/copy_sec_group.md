# 复制安全组 - CopySecGroup

## 简介

复制安全组






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CopySecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CopySecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **SecGroupId** | string | 源安全组ID |**Yes**|
| **DstRegion** | string | 目的地域 |**Yes**|
| **DstProjectId** | string | 目的项目ID |**Yes**|
| **DstVPCId** | string | 目的VPC ID |**Yes**|
| **DstName** | string | 目的安全组名称，最长64个字符 |No|
| **DstRemark** | string | 目的安全组备注 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SecGroupId** | string | 复制得到的安全组ID |**Yes**|
| **RuleID** | array[string] | 复制得到的规则ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CopySecGroup
&Region=cn-zj
&ProjectId=YJfISRjR
&SecGroupId=xZUDAEpK
&DstRegion=gAoInAjZ
&DstProjectId=rascbbHW
&DstVPCId=AaCZFxWd
&DstName=BMbNwgSI
&DstRemark=tKifgccS
```

### 响应示例
    
```json
{
  "Action": "CopySecGroupResponse",
  "Message": "FKIDYOVG",
  "RetCode": 0,
  "RuleID": [
    "qJGurXGD"
  ],
  "SecGroupId": "VqNyuEbd"
}
```





