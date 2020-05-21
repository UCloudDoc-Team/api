# 新的误报接口 - ModifyWafAttackFalseAlarmStatus

## 简介

添加误报 取消误报操作都在这个接口








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyWafAttackFalseAlarmStatus`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SetStatus** | string | 枚举值，SetFalseAlarm:标记误报,UnsetFalseAlarm：取消误报 |**Yes**|
| **Key** | string | 记录的 ID值 作为Key传递 |**Yes**|
| **FullDomain** | string | 要操作的域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyWafAttackFalseAlarmStatus
&ProjectId=org-xxx
&FullDomain=www.test.com
&Key=1111
&SetStatus=SetFalseAlarm
```

### 响应示例
    
```json
{
  "Action": "ModifyWafAttackFalseAlarmStatusResponse",
  "RetCode": 0
}
```





