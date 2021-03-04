# 更新ACL的规则 - UpdateNetworkAclEntry

## 简介

更新ACL的规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateNetworkAclEntry)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateNetworkAclEntry`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AclId** | string | ACL的ID |**Yes**|
| **EntryId** | string | 需要更新的Entry Id |**Yes**|
| **Priority** | int | Entry的优先级，对于同样的Direction来说，不能重复 |**Yes**|
| **Direction** | string | 出向或者入向（“Ingress”, "Egress") |**Yes**|
| **IpProtocol** | string | 针对的协议规则 |**Yes**|
| **CidrBlock** | string | IPv4段的CIDR表示 |**Yes**|
| **PortRange** | string | 针对的端口范围 |**Yes**|
| **EntryAction** | string | 规则的行为("Accept", "Reject") |**Yes**|
| **Description** | string | 描述 |No|
| **TargetType** | int | 应用目标类型。0代表“子网内全部资源”， 1代表“子网内指定资源”。默认为0 |No|
| **TargetResourceIds.N** | string | 应用目标资源列表。默认为全部资源生效。TargetType为0时不用填写该值 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateNetworkAclEntry
&Region=cn-bj
&AclId=netacl-xxxxxx
&EntryId=netaclentry_xxxxxx
&Priority=4
&Direction=Ingress
&IpProtocol=TCP
&CidrBlock=0.0.0.0/0
&PortRange=1-65535
&EntryAction=WefbebUQ
&Description=kazGjdPZ
&TargetType=4
&TargetResourceIds.n=JNflNaTv
```

### 响应示例
    
```json
{
  "Action": "UpdateNetworkAclEntryResponse",
  "RetCode": 0
}
```





