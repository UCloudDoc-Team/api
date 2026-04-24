# 获取某一类木马告警的详细描述信息 - GetUhostsecTrojanDescription

## 简介

获取某一类木马告警的详细描述信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUhostsecTrojanDescription`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **TableName** | string | 获取指定当前木马对应的告警表名，指定当前木马对应的告警表名，利用告警表名来获取当前的描述信息,可以通过获取ListUHostsecTrojanWarnsResponse的返回信息提供TableName值内容，值：WebShellAlarm、checkCockhorse |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Description** | string | 木马描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUhostsecTrojanDescription
&ProjectId=cn-zj
&TableName=XtXZlSOL
```

### 响应示例
    
```json
{
  "Action": "GetUhostsecTrojanDescriptionResponse",
  "Description": {},
  "RetCode": 0
}
```





