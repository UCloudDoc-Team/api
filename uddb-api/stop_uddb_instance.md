# 关闭UDDB实例 - StopUDDBInstance

## 简介

关闭UDDB实例，停止提供服务。<br /><br />如下状态的UDDB实例可以进行这个操作:<br /><br />Running: 正常运行中<br />Abnormal: 异常运行中<br />当请求返回成功之后，UDDB实例的状态变成"Shutdown"(关闭中); 如果返回失败, UDDB实例状态保持不变 UDDB实例在关闭过程中, 当UDDB实例关闭成功之后, UDDB实例的状态变成"Shutoff"(已关闭); 如果关闭过程中出现异常, 根据UDDB实例的情况, 状态变成"Abnormal"(异常运行中), 或者"Running"(正常运行中)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=StopUDDBInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StopUDDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UDDBId** | string | UDDB实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StopUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=jqMXBXkT
&ProjectId=kOeeSRbs
```

### 响应示例
    
```json
{
  "Action": "StopUDDBInstanceResponse",
  "Message": "WMrpfugk",
  "RetCode": 0
}
```





