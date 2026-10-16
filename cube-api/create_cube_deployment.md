# 创建容器实例Deployment - CreateCubeDeployment

## 简介

创建容器实例Deployment









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCubeDeployment`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPCId** | string | Deployment所属VPC |**Yes**|
| **SubnetId** | string | Deployment所属子网 |**Yes**|
| **Deployment** | string | Deployment yaml，使用base64编码 |**Yes**|
| **Name** | string | Deployment名称 |No|
| **CpuPlatform** | string | CPU平台 |No|
| **ChargeType** | string | 计费模式 |No|
| **Quantity** | string | 数量，默认为1 |No|
| **Tag** | string | 标签 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DeploymentId** | string | Deployment ID |**Yes**|
| **Deployment** | string | Deployment yaml，使用base64编码 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCubeDeployment
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=knRwpoqg
&VPCId=VDWDLulC
&SubnetId=KZpyFyVz
&Deployment=FbkxhnjG
&Name=ySstgXii
&CpuPlatform=iJjhuUEn
&ChargeType=yAyCZsat
&Quantity=uvSmgEPH
&Tag=JgYZwMbE
```

### 响应示例
    
```json
{
  "Action": "CreateCubeDeploymentResponse",
  "Deployment": "SZgOdnif",
  "DeploymentId": "ijhGDOoq",
  "RetCode": 0
}
```





