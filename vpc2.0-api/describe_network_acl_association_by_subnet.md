# 获取子网的ACL绑定信息 - DescribeNetworkAclAssociationBySubnet

## 简介

获取子网的ACL绑定信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkAclAssociationBySubnet)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkAclAssociationBySubnet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SubnetworkId** | string | 子网的ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Association** | [*AssociationInfo*](#AssociationInfo) | 绑定信息 |**Yes**|

#### 数据模型


#### AssociationInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AssociationId** | string | 绑定ID |**Yes**|
| **VpcId** | string | 所属的VPC ID |**Yes**|
| **AclId** | string | ACL的ID |**Yes**|
| **SubnetworkId** | string | 绑定的子网ID |**Yes**|
| **CreateTime** | int | 创建的Unix时间戳 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNetworkAclAssociationBySubnet
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId=subnet-xxxxxx
```

### 响应示例
    
```json
{
  "Action": "DescribeNetworkAclAssociationBySubnetResponse",
  "AssociationList": [
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 1,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 9,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 9,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 10,
      "SubnetworkId": "subnet-xxxxxx"
    }
  ],
  "RetCode": 0
}
```





