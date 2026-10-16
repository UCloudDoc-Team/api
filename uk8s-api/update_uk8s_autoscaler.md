# 更新伸缩器 - UpdateUK8SAutoscaler

## 简介

更新集群级缩容阈值和等待时间。调用前必须关闭 cluster-autoscaler；修改后重新开启，使新配置生效。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUK8SAutoscaler`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群ID |**Yes**|
| **ScaleDownUnneededTime** | int | 节点持续不需要后触发缩容的等待时间，单位分钟，范围 1–1440。 |**Yes**|
| **ScaleDownUtilizationThreshold** | int | 节点缩容利用率阈值，单位百分比，范围 0–100。例如 50 表示 50%。 |**Yes**|
| **ScaleDownDelayAfterAdd** | int | 添加节点后等待缩容的时间，单位分钟，范围 1–1440。 |**Yes**|
| **ScaleDownGPUUtilizationThreshold** | int | GPU 缩容利用率阈值，单位百分比，范围 0–100。省略时使用 ScaleDownUtilizationThreshold。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUK8SAutoscaler
&Region=cn-zj
&ProjectId=MhyFaNhs
&ClusterId=zjkQIvXU
&ScaleDownUnneededTime=3
&ScaleDownUtilizationThreshold=3
&ScaleDownDelayAfterAdd=7
&ScaleDownGPUUtilizationThreshold=5
```

### 响应示例
    
```json
{
  "Action": "UpdateUK8SAutoscalerResponse",
  "RetCode": 0
}
```





