# 获取域名请求数 - GetULiveDomainRequestInfo

## 简介

获取域名请求数






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveDomainRequestInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveDomainRequestInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | string | 开始时间，时间戳 |**Yes**|
| **EndTime** | string | 结束时间，时间戳 |**Yes**|
| **Type** | int | 带宽查询粒度，0：5分钟；1：1小时；2：1天； 3：1分钟 |**Yes**|
| **Domain** | string | 域名，可多选，可单选，可不选（默认查询账户下所有域名） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*RequestList*](#RequestList)] |  |No|

#### 数据模型


#### RequestList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间 |**Yes**|
| **Value** | int | 请求数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveDomainRequestInfo
&ProjectId=tcIdPQNd
&Domain=MFnIfvFn
&BeginTime=bVIjJWHb
&EndTime=hIkkQsDi
&Type=7
```

### 响应示例
    
```json
{
  "Action": "GetULiveDomainRequestInfoResponse",
  "Data": [
    {
      "Time": 4,
      "Value": 5
    }
  ],
  "RetCode": 0
}
```





