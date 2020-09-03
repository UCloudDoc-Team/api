# 删除UK8S集群 - DelUK8SCluster

## 简介

删除UK8S集群









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DelUK8SCluster`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 所属区域 |**Yes**|
| **ProjectId** | string | 项目id |No|
| **ClusterId** | string | 集群id |**Yes**|
| **ReleaseUDisk** | boolean | 是否删除节点挂载的数据盘。枚举值[true:删除，false: 不删除]，默认不删除 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ErrMsg** | string | 返回错误消息，当 RetCode 非 0 时提供详细的描述信息	 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DelUK8SCluster
&Region=gySoehip
&Zone=fhfpHbDR
&ClusterID=GGNfKAhZ
&ProjectID=JwRrSANU
&ReleaseUDisk=true
```

### 响应示例
    
```json
{
  "Action": "DelUK8SClusterResponse",
  "RetCode": 0
}
```





