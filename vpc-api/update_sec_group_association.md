# 更换安全组绑定关系 - UpdateSecGroupAssociation

## 简介

仅对操作的安全组ID生效，其他已有的绑定关系不受影响。



!> 该接口用于对单个资源先解绑部分安全组（参数 OldSecGroupId），再绑定部分安全组（NewPrioritySecGroup）。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateSecGroupAssociation)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateSecGroupAssociation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | 资源ID |**Yes**|
| **OldSecGroupId.N** | string | 被替换的安全组ID。支持数组格式，即为 string 数组。 |**Yes**|
| **NewPrioritySecGroup.N.Priority** | int | 新绑定安全组的绑定优先级。支持 NewPrioritySecGroup 为数组格式，即传对应数据的 JSON 格式数组。 |**Yes**|
| **NewPrioritySecGroup.N.SecGroupId** | string | 需新绑定的安全组ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateSecGroupAssociation
&Region=AARqFomP
&ProjectId=NLyPDsnf
&SecGroupId.n=fqWNNxvJ
&ResourceId.n=ercRryXn
&NewSecGroupId.n=RQrYZhoX
&NewPrioritySecGroup.N.SecGroupId=sMwScEex
```

### 响应示例
    
```json
{
  "Action": "UpdateSecGroupAssociationResponse",
  "RetCode": 0
}
```





