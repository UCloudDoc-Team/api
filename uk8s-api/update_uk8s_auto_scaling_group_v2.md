# 集群修改伸缩组V2 - UpdateUK8SAutoScalingGroupV2

## 简介

更新伸缩组的名称、节点数上下限和优先级。节点规格等配置请通过关联节点池修改。








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUK8SAutoScalingGroupV2`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，可选。此接口按集群和伸缩组 ID 更新配置。 |No|
| **ProjectId** | string | 项目ID |No|
| **Region** | string | 地域 |**Yes**|
| **ClusterId** | string | 集群ID |**Yes**|
| **Id** | string | 伸缩组ID |**Yes**|
| **Name** | string | 伸缩组名称 |**Yes**|
| **Min** | int | 最小节点数，范围 0–100。 |**Yes**|
| **Max** | int | 最大节点数，范围 1–100。 |**Yes**|
| **Priority** | int | 伸缩组优先级，范围 1–100，值越大越优先。省略或传 0 时保持原优先级。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUK8SAutoScalingGroupV2
&Zone=PWjhKooi
&ProjectId=RMTtolvk
&Region=CbyaHHww
&ClusterId=rgYejpNn
&Min=2
&Max=4
&Id=gfdWtBHO
&Name=mRWzEyJl
&Priority=2
```

### 响应示例
    
```json
{
  "Action": "UpdateUK8SAutoScalingGroupV2Response",
  "Id": "qVbRduxj",
  "Message": "frGgkagO",
  "RetCode": 0
}
```





