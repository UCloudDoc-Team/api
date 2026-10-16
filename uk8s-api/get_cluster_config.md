# 获取集群配置文件 - GetClusterConfig

## 简介

获取集群配置文件，管理集群的凭证









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetClusterConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 所在项目 |No|
| **Region** | string | 所在区域 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KubeConfig** | string | 配置信息 |**Yes**|
| **ExternalKubeConfig** | string | 开启公网apiserver的情况下，有数据返回。 |No|
| **Updatable** | boolean | 用于标示 kubeconfig 是否可以进行替换更新 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetClusterConfig
&AzGroup=OMHXXfyW
&Zone=cnWbQGjo
&ProjectID=ASjvFawh
&ClusterID=DywdxtWZ
```

### 响应示例
    
```json
{
  "Action": "GetClusterConfigResponse",
  "ExternalKubeConfig": "PhycEJji",
  "RetCode": 0,
  "Updatable": true
}
```





