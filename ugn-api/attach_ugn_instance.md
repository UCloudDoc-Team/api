# 实例加入云联网 - AttachUGNInstance

## 简介

实例加入云联网









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AttachUGNInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNId** | string | 云联网Id |**Yes**|
| **InstanceId** | string | 实例Id |**Yes**|
| **InstanceType** | string | 实例类型 |**Yes**|
| **InstanceRegion** | string | 实例归属地域 |**Yes**|
| **InstanceProjectId** | string | 实例归属ProjectId |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AttachUGNInstance
&ProjectId=BaWJrGAB
&UGNId=OxUOKFwy
&InstanceId=jgBAcojQ
&InstanceType=vpc
&InstanceRegion=PIAwXWul
&InstanceProjectId=ldBNTCAs
```

### 响应示例
    
```json
{
  "Action": "AttachUGNInstanceResponse",
  "Message": "success",
  "RetCode": 0
}
```





