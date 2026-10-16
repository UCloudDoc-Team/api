# 查询下载数据最新更新时间 - QueryNewestUpdateTime

## 简介

查询下载数据最新更新时间









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryNewestUpdateTime`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*DataSignatureNewestUpdateTime*](#DataSignatureNewestUpdateTime) | 数据最新更新时间 |**Yes**|

#### 数据模型


#### DataSignatureNewestUpdateTime

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Torojan** | string | 木马样本最新更新时间 |No|
| **WebBase** | string | web基线最新更新时间 |No|
| **Webshell** | string | Webshell最新更新时间 |No|
| **Vul** | string | 漏洞最新更新时间 |No|
| **Login** | string | 登录流水最新更新时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryNewestUpdateTime
&ProjectId=iAwUGjvD
```

### 响应示例
    
```json
{
  "Action": "QueryNewestUpdateTimeResponse",
  "Result": {
    "Login": "Wed May 30 15:45:37 2018",
    "Torojan": "2018-02-18 00:00:00",
    "Vul": "2018-09-18 15:22:18",
    "WebBase": "2018-08-30 19:25:56",
    "Webshell": "2018-08-24 17:39:34",
    "WeekReport": "2018-08-24 17:39:34"
  },
  "RetCode": 0
}
```





