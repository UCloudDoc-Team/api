# 获取 uk8s  LoadBalancerController - GetUK8SLoadBalancerController

## 简介

获取 uk8s  LoadBalancerController 信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SLoadBalancerController`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，可选。 |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群 id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LastVersion** | string | 最新可用版本。 |**Yes**|
| **Version** | string | 当前安装版本。 |**Yes**|
| **Installed** | boolean | 是否安装 |**Yes**|
| **CreateTime** | int | 安装时间，Unix 时间戳，单位秒。 |**Yes**|
| **Status** | string | 运行状态：unknown、running、notReady。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SLoadBalancerController
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=MhorCCvj
&ClusterId=EEVjjmri
&ClusterId=DKpKDIiu
```

### 响应示例
    
```json
{
  "Action": "GetUK8SLoadBalancerControllerResponse",
  "CreateTime": 5,
  "Installed": false,
  "LastVersion": "FGcJfFPv",
  "RetCode": 0,
  "Status": "unknown",
  "Version": "DGsbQHZv"
}
```





