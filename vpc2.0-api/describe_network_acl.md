# 获取网络ACL - DescribeNetworkAcl

## 简介

获取网络ACL






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkAcl)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkAcl`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 列表偏移量 |No|
| **Limit** | string | 列表获取的个数限制 |No|
| **VpcId** | string | 需要获取的ACL所属的VPC的ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AclList** | array[[*AclInfo*](#AclInfo)] | ACL的信息，具体结构见下方AclInfo |**Yes**|

#### 数据模型


#### AclInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VpcId** | string | ACL所属的VPC ID |**Yes**|
| **AclId** | string | ACL的ID |**Yes**|
| **AclName** | string | 名称 |**Yes**|
| **Description** | string | 描述 |**Yes**|
| **Entries** | array[[*AclEntryInfo*](#AclEntryInfo)] | 所有的规则 |**Yes**|
| **Associations** | array[[*AssociationInfo*](#AssociationInfo)] | 所有的绑定关系，具体结构见下方AssociationInfo |**Yes**|
| **CreateTime** | int | 创建的Unix时间戳 |**Yes**|
| **UpdateTime** | int | 更改的Unix时间戳 |**Yes**|

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

#### AssociationInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AssociationId** | string | 绑定ID |**Yes**|
| **VpcId** | string | 所属的VPC ID |**Yes**|
| **AclId** | string | ACL的ID |**Yes**|
| **SubnetworkId** | string | 绑定的子网ID |**Yes**|
| **CreateTime** | int | 创建的Unix时间戳 |**Yes**|

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
https://api.ucloud.cn/?Action=DescribeNetworkAcl
&Region=cn-bj
&ProjectId=org-xxxxx
&VpcId=uvnet-xxxxxx
&Offset=2
&Limit=vTnIQqcI
```

### 响应示例
    
```json
{
  "AclList": [
    {
      "AclId": "netacl-xxxxxx",
      "AclName": "sdfsdfsdf",
      "Associations": [
        {
          "AclId": "netacl-xxxxxx",
          "AssociationId": "netaclassoc_xxxxxx",
          "CreateTime": 2,
          "SubnetworkId": "subnet-xxxxxx"
        }
      ],
      "CreateTime": 4,
      "Description": "",
      "Entries": [
        {
          "CidrBlock": "0.0.0.0/0",
          "CreateTime": 1,
          "Description": "sdsdsd",
          "Direction": "Ingress",
          "EntryAction": "Accept",
          "EntryId": "netaclentry_xxxxxx",
          "IpProtocol": "TCP",
          "PortRange": "All",
          "Priority": "100",
          "TargetResourceCount": 0,
          "TargetResourceList": null,
          "TargetType": 0,
          "UpdateTime": 8
        },
        {
          "CidrBlock": "0.0.0.0/0",
          "CreateTime": 3,
          "Description": "sdsdsfd",
          "Direction": "Egress",
          "EntryAction": "Accept",
          "EntryId": "netaclentry_xxxxxx",
          "IpProtocol": "TCP",
          "PortRange": "All",
          "Priority": "1000",
          "TargetResourceCount": 0,
          "TargetResourceList": null,
          "TargetType": 0,
          "UpdateTime": 2
        }
      ],
      "UpdateTime": 5,
      "VpcId": "uvnet-xxxxxx"
    },
    {
      "AclId": "netacl-xxxxxx",
      "AclName": "DKLGHDhfdj",
      "Associations": null,
      "CreateTime": 1,
      "Description": "BVJDOIFdkf",
      "Entries": [
        {
          "CidrBlock": "10.10.10.10/32",
          "CreateTime": 4,
          "Description": "vdfdgg",
          "Direction": "Egress",
          "EntryAction": "Reject",
          "EntryId": "netaclentry_xxxxxx",
          "IpProtocol": "TCP",
          "PortRange": "All",
          "Priority": "100",
          "TargetResourceCount": 0,
          "TargetResourceList": null,
          "TargetType": 0,
          "UpdateTime": 7
        },
        {
          "CidrBlock": "10.10.10.10/32",
          "CreateTime": 6,
          "Description": "uykj",
          "Direction": "Ingress",
          "EntryAction": "Reject",
          "EntryId": "netaclentry_xxxxxx",
          "IpProtocol": "TCP",
          "PortRange": "All",
          "Priority": "1000",
          "TargetResourceCount": 0,
          "TargetResourceList": null,
          "TargetType": 0,
          "UpdateTime": 9
        }
      ],
      "UpdateTime": 3,
      "VpcId": "uvnet-xxxxxx"
    }
  ],
  "Action": "DescribeNetworkAclResponse",
  "RetCode": 0,
  "TotalCount": 2
}
```





