# 获取网络ACL的绑定关系列表 - DescribeNetworkAclAssociation

## 简介

获取网络ACL的绑定关系列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkAclAssociation)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkAclAssociation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AclId** | string | Acl的ID |**Yes**|
| **Offset** | int | 列表偏移量 |No|
| **Limit** | string | 列表获取的个数限制 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AssociationList** | array[[*AssociationInfo*](#AssociationInfo)] | 绑定信息列表 |**Yes**|

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
https://api.ucloud.cn/?Action=DescribeNetworkAclAssociation
&Region=cn-bj
&ProjectId=org-xxxxx
&AclId=netacl-xxxxxx
&Offset=6
&Limit=5
```

### 响应示例
    
```json
{
  "Action": "DescribeNetworkAclAssociationResponse",
  "AssociationList": [
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 1583374605,
      "SubnetworkId": "subnet-xxxxxx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





