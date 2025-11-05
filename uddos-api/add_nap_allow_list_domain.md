# 添加域名允许列表 - AddNapAllowListDomain

## 简介

添加域名允许列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddNapAllowListDomain)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddNapAllowListDomain`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **Domain.N** | string | 域名，N从0开始，多个域名：Domain.0、Domain.1、... |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*DomainConfigResult*](#DomainConfigResult)] | 域名配置结果 |No|

#### 数据模型


#### DomainConfigResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **Code** | int | 错误码 |**Yes**|
| **Message** | string | 提示信息 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddNapAllowListDomain
&ResourceId=xGhMbZOs
&Domain.0=ucloud.cn
```

### 响应示例
    
```json
{
  "Action": "AddNapAllowListDomainResponse",
  "Data": [
    {
      "Code": 0,
      "Domain": "ucloud.cn",
      "Message": "success"
    }
  ],
  "RetCode": 0
}
```





