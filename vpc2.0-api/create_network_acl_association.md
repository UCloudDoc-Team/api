# 创建ACL的绑定关系 - CreateNetworkAclAssociation

## 简介

创建ACL的绑定关系









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNetworkAclAssociation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AclId** | string | ACL的ID |**Yes**|
| **SubnetworkId** | string | 需要绑定的子网ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AclId** | string | Acl的ID |**Yes**|
| **AssociationId** | string | 创建的绑定关系的ID |**Yes**|
| **PrevAssociation** | [*AssociationInfo*](#AssociationInfo) | 该子网之前的绑定关系信息 |No|

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
https://api.ucloud.cn/?Action=CreateNetworkAclAssociation
&VpcId=uvnet-xxxxxx
&AclId=netacl-xxxxxx
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId=subnet-xxxxxx
```

### 响应示例
    
```json
{
  "Action": "CreateNetworkAclAssociationResponse",
  "AssociationId": "netaclassoc_xxxxxx",
  "PrevAssociation": [
    {
      "AclId": "netacl-xxxxxx",
      "AssociationId": "netaclassoc_xxxxxx",
      "CreateTime": 3,
      "SubnetworkId": "subnet-xxxxxx"
    }
  ],
  "RetCode": 0
}
```





