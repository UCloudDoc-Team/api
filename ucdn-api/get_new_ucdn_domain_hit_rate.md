# 获取域名命中率 - GetNewUcdnDomainHitRate

## 简介

获取域名命中率






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnDomainHitRate)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnDomainHitRate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Type** | int | 时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度） |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外，只支持国内 |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间。 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HitRateList** | array[[*HitRateInfo*](#HitRateInfo)] | 请求数实例表。 |No|

#### 数据模型


#### HitRateInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **FlowHitRate** | float | 流量命中率，单位% |No|
| **RequestHitRate** | float | 请求数命中率，单位% |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainHitRate
&DomainId.n=kdINXUac
&Areacode=OvvqAfwC
&BeginTime=5
&EndTime=1
&Type=9
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnDomainHitRateResponse",
  "RequestList": [
    {
      "CdnRequest": 8,
      "OriginRequest": 4,
      "Time": 6
    },
    {
      "CdnRequest": 2,
      "OriginRequest": 1,
      "Time": 4
    },
    {
      "CdnRequest": 6,
      "OriginRequest": 2,
      "Time": 1
    },
    {
      "CdnRequest": 2,
      "OriginRequest": 9,
      "Time": 9
    },
    {
      "CdnRequest": 1,
      "OriginRequest": 1,
      "Time": 7
    },
    {
      "CdnRequest": 4,
      "OriginRequest": 6,
      "Time": 8
    },
    {
      "CdnRequest": 3,
      "OriginRequest": 8,
      "Time": 8
    }
  ],
  "RetCode": 0
}
```





