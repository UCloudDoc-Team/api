# 查询SVC信息 - DescribeSVC

## 简介

查询SVC信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSVC)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSVC`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SvcName** | string | 服务名 |No|
| **ClusterId** | string | 集群ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SvcSet** | array[[*SvcSet*](#SvcSet)] | 服务信息 |No|

#### 数据模型


#### SvcSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SvcName** | string | 服务名 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **ProxyCount** | int | 代理数目 |**Yes**|
| **PodCount** | int | Pod数目 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSVC
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&SvcName=tttt
&ClusterId=cluster-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeSVCResponse",
  "RetCode": 0,
  "SvcSet": [
    {
      "ClusterId": "cluster-xxx",
      "PodCount": 3,
      "PortMap": {
        "80": "80"
      },
      "ProxyCount": 1,
      "Status": "running",
      "SvcName": "tttt"
    }
  ]
}
```





