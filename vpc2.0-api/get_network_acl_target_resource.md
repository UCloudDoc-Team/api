# 获取ACL规则应用目标列表 - GetNetworkAclTargetResource

## 简介

获取ACL规则应用目标列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNetworkAclTargetResource)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNetworkAclTargetResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SubnetworkId.N** | string | 子网ID。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TargetResourceList** | array[[*TargetResourceInfo*](#TargetResourceInfo)] | ACL规则应用目标资源列表，具体结构见下方TargetResourceInfo |**Yes**|
| **TotalCount** | int | ACL规则应用目标资源总数 |**Yes**|

#### 数据模型


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
https://api.ucloud.cn/?Action=GetNetworkAclTargetResource
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId.n=subnet-xxxxxx
```

### 响应示例
    
```json
{
  "Action": "GetNetworkAclTargetResourceResponse",
  "RetCode": 0,
  "TargetResourceList": [
    {
      "PrivateIp": "10.23.x.x",
      "ResourceId": "udb-xxxxxx",
      "ResourceName": "UDB",
      "ResourceType": 6,
      "SubResourceId": "",
      "SubResourceName": "",
      "SubResourceType": 0,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "PrivateIp": "10.19.x.x",
      "ResourceId": "uhost-xxxxxx",
      "ResourceName": "UHost",
      "ResourceType": 6,
      "SubResourceId": "",
      "SubResourceName": "",
      "SubResourceType": 0,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "PrivateIp": "10.23.x.x",
      "ResourceId": "uredis-xxxxxx",
      "ResourceName": "URedis",
      "ResourceType": 6,
      "SubResourceId": "",
      "SubResourceName": "",
      "SubResourceType": 0,
      "SubnetworkId": "subnet-xxxxxx"
    },
    {
      "PrivateIp": "10.23.x.x",
      "ResourceId": "uhadoop-xxxxxx",
      "ResourceName": "UHadoop",
      "ResourceType": 6,
      "SubResourceId": "",
      "SubResourceName": "",
      "SubResourceType": 0,
      "SubnetworkId": "subnet-xxxxxx"
    }
  ],
  "TotalCount": 2
}
```





