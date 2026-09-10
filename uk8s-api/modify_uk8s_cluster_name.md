# 修改k8s集群名称 - ModifyUK8SClusterName

## 简介

修改k8s集群名称









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyUK8SClusterName`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |No|
| **Region** | string | 所在地域 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **ClusterName** | string | 集群名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyUK8SClusterName
&ProjectId=DWkrTXGw
&ClusterID=LNAxnxhF
&Name=TSqUXbKT
&AzGroup=OdqSIeWo
```

### 响应示例
    
```json
{
  "Action": "ModifyUK8SClusterNameResponse",
  "RetCode": 0
}
```





