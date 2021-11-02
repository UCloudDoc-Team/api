# 获取域名状态码监控 - GetULiveDomainHttpCode

## 简介

获取域名状态码监控






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveDomainHttpCode)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveDomainHttpCode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | int |  时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度,3表示按照一分钟粒度) |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间 |No|
| **Areacode** | string |   查询带宽区域 cn代表国内 abroad代表海外，只支持国内 |No|
| **Layer** | string | 指定获取的状态码是边缘还是上层 edge 表示边缘 layer 表示上层 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HttpCodeDetail** | array[[*HttpCodeInfo*](#HttpCodeInfo)] | HTTP状态码详细信息 |No|

#### 数据模型


#### HttpCodeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **Http2XX** | [*HttpCode2XX*](#HttpCode2XX) | 2xx的数量,参考HttpCode2XX结构 |No|
| **Http4XX** | [*HttpCode4XX*](#HttpCode4XX) | 4xx的数量,参考HttpCode4XX结构 |No|
| **Http5XX** | [*HttpCode5XX*](#HttpCode5XX) | 5xx的数量,参考HttpCode5XX结构 |No|

#### HttpCode2XX

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Http200** | int | 状态码200的数量 |No|
| **Total** | int | 2xx总的数量 |No|

#### HttpCode4XX

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Http403** | int | 403状态码的数量 |No|
| **Http404** | int | 404状态码的数量 |No|
| **Total** | int | 4xx状态码总的数量 |No|

#### HttpCode5XX

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Http503** | int | 503状态码的数量 |No|
| **Http504** | int | 504状态码的数量 |No|
| **Total** | int | 5xx状态码总的数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveDomainHttpCode
&ProjectId=vtpBRKFV
&Type=2
&DomainId.n=yTfuSpLX
&BeginTime=7
&EndTime=2
&Areacode=QIRRxczM
&Layer=sEbvJSPs
```

### 响应示例
    
```json
{
  "Action": "GetULiveDomainHttpCodeResponse",
  "HttpCodeDetail": [
    {
      "Http2XX": {},
      "Http4XX": {},
      "Http5XX": {},
      "Time": 1
    }
  ],
  "RetCode": 0
}
```





