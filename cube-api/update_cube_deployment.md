# 更新Deployment - UpdateCubeDeployment

## 简介

更新Deployment









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateCubeDeployment`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DeploymentId** | string | Deployment的Id |**Yes**|
| **Deployment** | string | base64编码的Deployment的yaml。大小不超过16KB |**Yes**|
| **Name** | string | Deployment的name |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Deployment** | string | 经过base64编码的Deployment的yaml |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateCubeDeployment
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=OgkWqqSd
&ControllerId=IhUdGKtC
&Yaml=YNXiZfNH
&Name=RALnSnij
```

### 响应示例
    
```json
{
  "Action": "UpdateCubeDeploymentResponse",
  "Deployment": "BvXwsxaF",
  "RetCode": 0
}
```





