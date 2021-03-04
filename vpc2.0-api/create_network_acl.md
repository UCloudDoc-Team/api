# 创建网络ACL - CreateNetworkAcl

## 简介

创建网络ACL









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNetworkAcl`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **VpcId** | string | 将要创建的ACL所属VPC的ID |**Yes**|
| **AclName** | string | ACL的名称 |**Yes**|
| **Description** | string | ACL的描述 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AclId** | string | 创建的ACL的ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateNetworkAcl
&VpcId=uvnet-xxxxxx
&AclName=CSMmTACF
&Description=YDdjjiUK
&Region=cn-bj
&ProjectId=org-xxxxx
```

### 响应示例
    
```json
{
  "AclId": "netacl-xxxxxx",
  "Action": "CreateNetworkAclResponse",
  "RetCode": 0
}
```





