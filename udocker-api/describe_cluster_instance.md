# 获取Cluster实例 - DescribeClusterInstance

## 简介

获取Cluster实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeClusterInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeClusterInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ClusterIds.N** | string | Cluster实例ID,如果为空获取全部。n=0,1,2... |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | Container count |**Yes**|
| **ClusterSet** | string | Cluster实例set |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeClusterInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&ClusterIds.0=cluster-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeClusterInstanceResponse",
  "ClusterSet": [
    {
      "CPU": 8,
      "ClusterId": "cluster-xxx",
      "ClusterName": "cluster2",
      "CreateTime": 1529984017,
      "Memory": 16384,
      "NodeCount": 2,
      "UsedCPU": "0.0",
      "UsedMem": 695,
      "VPCId": "uvnet-xxx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





