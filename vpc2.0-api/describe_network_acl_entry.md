# 获取ACL的规则信息 - DescribeNetworkAclEntry

## 简介

获取ACL的规则信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkAclEntry)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkAclEntry`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AclId** | string | ACL的ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **EntryList** | array[[*AclEntryInfo*](#AclEntryInfo)] | 所有的规则信息 |**Yes**|

#### 数据模型


#### AclEntryInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EntryId** | string | Entry的ID |**Yes**|
| **Priority** | string | 优先级 |**Yes**|
| **Direction** | string | 出向或者入向 |**Yes**|
| **IpProtocol** | string | 针对的IP协议 |**Yes**|
| **CidrBlock** | string | IP段的CIDR信息 |**Yes**|
| **PortRange** | string | Port的段信息 |**Yes**|
| **EntryAction** | string | 匹配规则的动作 |**Yes**|
| **TargetType** | int | 应用目标类型。 0代表“子网内全部资源” ，1代表“子网内指定资源” 。 |**Yes**|
| **CreateTime** | int | 创建的Unix时间戳 |**Yes**|
| **UpdateTime** | int | 更改的Unix时间戳 |**Yes**|
| **TargetResourceList** | array[[*TargetResourceInfo*](#TargetResourceInfo)] | 应用目标资源信息。TargetType为0时不返回该值。具体结构见下方TargetResourceInfo |No|
| **TargetResourceCount** | int | 应用目标资源数量。TargetType为0时不返回该值。 |No|

#### TargetResourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SubnetworkId** | string | 子网ID |**Yes**|
| **ResourceName** | string | 资源名称 |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **ResourceType** | int | 资源类型 |**Yes**|
| **SubResourceName** | string | 资源绑定的虚拟网卡的名称 |**Yes**|
| **SubResourceId** | string | 资源绑定的虚拟网卡的ID |**Yes**|
| **SubResourceType** | int | 资源绑定虚拟网卡的类型 |**Yes**|
| **PrivateIP** | string | 资源内网IP |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNetworkAclEntry
&Region=cn-bj
&ProjectId=org-xxxxx
&AclId=netacl-xxxxxx
```

### 响应示例
    
```json
{
  "Action": "DescribeNetworkAclEntryResponse",
  "EntryList": [
    {
      "CidrBlock": "0.0.0.0/0",
      "CreateTime": 9,
      "Description": "hgrDEGHjv",
      "Direction": "Ingress",
      "EntryAction": "Accept",
      "EntryId": "netaclentry_xxxxx",
      "IpProtocol": "TCP",
      "PortRange": "All",
      "Priority": "100",
      "TargetResourceCount": 0,
      "TargetResourceList": null,
      "TargetType": 0,
      "UpdateTime": 4
    },
    {
      "CidrBlock": "0.0.0.0/0",
      "CreateTime": 9,
      "Description": "hgrDEGHjv",
      "Direction": "Ingress",
      "EntryAction": "Accept",
      "EntryId": "netaclentry_xxxxx",
      "IpProtocol": "TCP",
      "PortRange": "All",
      "Priority": "100",
      "TargetResourceCount": 0,
      "TargetResourceList": null,
      "TargetType": 0,
      "UpdateTime": 4
    },
    {
      "CidrBlock": "0.0.0.0/0",
      "CreateTime": 9,
      "Description": "hgrDEGHjv",
      "Direction": "Egress",
      "EntryAction": "Accept",
      "EntryId": "netaclentry_xxxxx",
      "IpProtocol": "TCP",
      "PortRange": "All",
      "Priority": "1000",
      "TargetResourceCount": 0,
      "TargetResourceList": null,
      "TargetType": 0,
      "UpdateTime": 4
    },
    {
      "CidrBlock": "0.0.0.0/0",
      "CreateTime": 9,
      "Description": "hgrDEGHjv",
      "Direction": "Egress",
      "EntryAction": "Accept",
      "EntryId": "netaclentry_xxxxx",
      "IpProtocol": "TCP",
      "PortRange": "All",
      "Priority": "1000",
      "TargetResourceCount": 0,
      "TargetResourceList": null,
      "TargetType": 0,
      "UpdateTime": 4
    }
  ],
  "RetCode": 0
}
```





