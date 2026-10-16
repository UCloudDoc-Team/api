# 获取支持创建的UK8S集群版本 - GetUK8SVersions

## 简介

获取支持创建的UK8S集群版本、Containerd版本









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SVersions`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Kind** | string | 集群类型，可选值为[Dedicated] |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*UK8SVersionData*](#UK8SVersionData)] | UK8S 版本信息列表。 |No|

#### 数据模型


#### UK8SVersionData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **K8sVersion** | string | K8S 版本 |**Yes**|
| **ContainerdVersion** | string | Containerd 版本 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SVersions
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=HpWKrCAn
&Kind=dZwvEmzo
&Kind=mrCBphtc
&Region=bFIpFSaD
&ProjectId=abBjWZOD
&Kind=fyjsGLau
```

### 响应示例
    
```json
{
  "Action": "GetUK8SVersionsResponse",
  "ContainerdVersion": "piaBRUsB",
  "Data": {},
  "K8sVersion": "LgmQLmzB",
  "RetCode": 0
}
```





