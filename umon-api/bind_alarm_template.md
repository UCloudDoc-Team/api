# 绑定告警模板 - BindAlarmTemplate

## 简介

绑定告警模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BindAlarmTemplate)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BindAlarmTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，如下资源类型不需要：<br />'eip', 'sharebandwidth', 'ulb', 'ulb-vserver', 'ulb-server', 'vserver', 'ugc', 'upath'，'ugaa' |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AlarmTemplateId** | string | 告警模板id，调用GetAlarmTemplateList获取 |**Yes**|
| **ResourceType** | string | 资源类型，同DescribeResourceMetric支持的类型，请参考DescribeResourceMetric中的可选资源类型 |**Yes**|
| **ResourceId.N** | string | 短资源id列表 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BindAlarmTemplate
&ProjectId=org-xxx
&Zone=cn-bj2-02
&Region= cn-bj2
&AlarmTemplateId=xxxx
&ResourceType=uhost
&ResourceId.0=uhost-xxxxx
```

### 响应示例
    
```json
{
  "Action": "BindAlarmTemplateResponse",
  "RetCode": 0
}
```





