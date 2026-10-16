# 获取在线流列表控制台 - GetULiveDomRealStreamListInfo

## 简介

获取在线流列表控制台以及官网展示






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveDomRealStreamListInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveDomRealStreamListInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Domain** | string | 域名 |**Yes**|
| **Application** | string | 接入点 |No|
| **StreamName.N** | string | 流名称，可多选 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RealStreamList** | array[[*RealStreamList*](#RealStreamList)] | 	在线流列表 |**Yes**|

#### 数据模型


#### RealStreamList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |No|
| **StreamName** | string | 流名 |No|
| **Application** | string | 接入点 |No|
| **ClientIp** | string | 客户端ip |No|
| **BeginTime** | string | 推流开始时间 |No|
| **OnlineValue** | string | 观众在线人数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveDomRealStreamListInfo
&ProjectId=fjdCWzBD
&Domain=lxuwqmjm
&Application=HyDbdQjx
&StreamName.n=ytiDtdcE
```

### 响应示例
    
```json
{
  "Action": "GetULiveDomRealStreamListInfoResponse",
  "RealStreamList": [
    {
      "Application": "vJMoXwJO",
      "BeginTime": "MyQXetFJ",
      "ClientIp": "keNIIAXN",
      "Domain": "YZiFqYsE",
      "OnlineValue": "TzWsYzmp",
      "StreamName": "fngIJKsk"
    }
  ],
  "RetCode": 0
}
```





