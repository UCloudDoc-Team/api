# 创建 Group - CreateURocketMQGroup

## 简介

创建一个 Group, 如果同名 Group 在当前 Service 中已存在, 则会失败.









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateURocketMQGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Name** | string | Group 名称，支持大小写字母、数字及-, _ ，长度1\~36 |**Yes**|
| **Remark** | string | Group 描述. |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupId** | string | 新建 Group 的 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateURocketMQGroup
&Region=cn-zj
&ProjectId=DmivrrqJ
&ServiceId=kocObAiX
&Name=ZJvTtEun
&Remark=DSLubcQt
```

### 响应示例
    
```json
{
  "Action": "CreateURocketMQGroupResponse",
  "GroupId": "HqfBvXoa",
  "Message": "hZyhJkMh",
  "RetCode": 0
}
```





