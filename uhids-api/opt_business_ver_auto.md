# 操作自动设置企业版开关 - OptBusinessVerAuto

## 简介

对自动设置企业版的开关设置









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `OptBusinessVerAuto`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **Open** | boolean | 开(true)/关(false) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **OpenStatus** | boolean | 当前开关状态，false-关闭，true-开启 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=OptBusinessVerAuto
&Open=true
&ProjectId=DikVTAxN
```

### 响应示例
    
```json
{
  "Action": "OptBusinessVerAutoResponse",
  "OpenStatus": false,
  "RetCode": 0
}
```





