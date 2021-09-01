# 获取Cube的token - GetCubeToken

## 简介

获取Cube的token，可用于terminal登录、log获取









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCubeToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ContainerName** | string | 容器名称 |**Yes**|
| **CubeId** | string | CubeId 和 Uid 中必须填写任意一个。<br />CubeId 是所有 Cube 资源的唯一 ID，如非在 UK8S 通过 Virtual Kubelet 插件创建的 Cube， 则必填 CubeId |No|
| **Uid** | string | CubeId 和 Uid 中必须填写任意一个。<br />Uid 是在 UK8S 中通过 Virtual Kubelet 插件创建出的 Cube 的唯一标识 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Token** | string | 有效时间5min |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCubeToken
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=biMFeyWa
&ContainerName=OcGrrmUE
&CubeId=HeoglJxD
&Uid=DpFVluEg
```

### 响应示例
    
```json
{
  "Action": "GetCubeTokenResponse",
  "RetCode": 0,
  "TerminalUrl": "LKKmzYht",
  "Token": "QqjyGHqi"
}
```





