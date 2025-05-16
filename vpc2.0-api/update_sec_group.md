# 更新安全组基本信息 - UpdateSecGroup

## 简介

更新安全组基本信息

?> 批量使用数组




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateSecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateSecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SecGroupId** | string | 安全组资源ID数组。不支持 .n 格式。Type 为 string 数组。 |**Yes**|
| **Name** | string | 安全组名称，默认为空，为空则不做修改。Name,Tag,Remark必须填写1个及以上 |No|
| **Remark** | string | 安全组备注，默认为空，为空则不做修改。Name,Tag,Remark必须填写1个及以上 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateSecGroup
&Region=cn-zj
&ProjectId=jaJNDhuE
&VPCId=niVFVPGk
&Name=JHizsfmg
&Tag=iJMcYRQE
&Remark=EJrWyZcL
&SecGroupId.n=ivzIJLhI
```

### 响应示例
    
```json
{
  "Action": "UpdateSecGroupResponse",
  "RetCode": 0,
  "SecGroupId": "wUdGLOFL"
}
```





