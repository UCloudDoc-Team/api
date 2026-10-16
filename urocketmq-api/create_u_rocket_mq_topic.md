# 创建Topic - CreateURocketMQTopic

## 简介

创建一个Topic，如果同名 Topic 在当前 Service 中已存在, 则会失败.









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateURocketMQTopic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | Topic 名称. 正则检查: ^[a-zA-Z0-9-_]{1,36}$ |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **MessageType** | string | 消息类型，包括Normal:普通消息,PartitionSequence:分区顺序消息,GlobalSequence:全局顺序消息,Transaction:事务消息,Delay:延时消息 |**Yes**|
| **Remark** | string | Topic 描述. 正则检查: ^[<br /><br />s<br /><br />S]{0,36}$ |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TopicId** | string | 新建 Topic 的 ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateURocketMQTopic
&Region=cn-zj
&ProjectId=xBYBAiSJ
&Name=mmpReQXIFkEtjudCBrwcPpXtmvgWStmCIuWHfabanAJIrhdQzbRYCSeFrZwOkmUiHX
&ServiceId=cdgcOJmH
&MessageType=Normal
&Remark=yctVrcos
```

### 响应示例
    
```json
{
  "Action": "CreateURocketMQTopicResponse",
  "Message": "rlsxDqXE",
  "RetCode": 0,
  "TopicId": "PzMlAQNX"
}
```





