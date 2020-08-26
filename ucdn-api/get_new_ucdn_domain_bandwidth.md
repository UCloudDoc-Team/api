# 获取域名带宽数据 - GetNewUcdnDomainBandwidth

## 简介

获取域名带宽数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnDomainBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnDomainBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Type** | int | 时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度） |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外 不填默认为全部区域 |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间。 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthList** | array[[*BandwidthInfo*](#BandwidthInfo)] | 带宽信息列表，参见BandwidthInfo |No|
| **Traffic** | float | 从起始时间到结束时间内的所使用的CDN总流量，单位GB |No|

#### 数据模型


#### BandwidthInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **CdnBandwidth** | float | 返回值返回指定时间区间内CDN的带宽峰值，单位Mbps（如果请求参数Type为0，则Value是五分钟粒度的带宽值，如果Type为1，则Value是1小时的带宽峰值，如果Type为2，则Value是一天内的带宽峰值） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainBandwidth
&ProjectId=org-xxxxx
&DomainId.n=KrgnhdNW
&Areacode=nallEbvw
&BeginTime=1
&EndTime=9
&Type=6
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnDomainBandwidthResponse",
  "BandwidthList": [
    {
      "CdnBandwidth": 7.16981,
      "OriginBandwidth": 6.21946,
      "Time": 6
    },
    {
      "CdnBandwidth": 9.33524,
      "OriginBandwidth": 5.85159,
      "Time": 6
    },
    {
      "CdnBandwidth": 5.84444,
      "OriginBandwidth": 5.55357,
      "Time": 3
    }
  ],
  "RetCode": 0,
  "Traffic": 8.33753
}
```





