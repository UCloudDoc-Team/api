# 获取IP基础攻击条目信息 - GetUSAIpAtkBriefEvents

## 简介

获取IP基础攻击条目信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSAIpAtkBriefEvents`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为100 |No|
| **BeginTime** | int | 起始时间，需使用时间戳 |No|
| **EndTime** | int | 结束时间，需使用时间戳，结束时间需大于起始时间 |No|
| **Ip** | string | 需要获取攻击条目的IP地址 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int |  |**Yes**|
| **AtkEvents** | array[[*IpAtkBriefEvent*](#IpAtkBriefEvent)] |  |**Yes**|

#### 数据模型


#### IpAtkBriefEvent

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | int | Ip所处Region |No|
| **Ip** | string | IP地址 |No|
| **Type** | int | Ip地址类型 |No|
| **AtkPeakBps** | string | bps峰值 (Mbps) |No|
| **AtkPeakPps** | string | pps峰值 |No|
| **AtkType** | string | 攻击类型 |No|
| **AtkStartTime** | int | 攻击开始时间 |No|
| **CostTime** | int | 持续的时间 |No|
| **PktFileUrl** | string | 下载包的位置 |No|
| **DetailId** | int | -1没有数据, 其他情况指明详细的I |No|
| **MoreDetail** | int | 0 没有详细信息,  1表明有详细信息 |No|
| **EventId** | int | 本攻击事件的Id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSAIpAtkBriefEvents
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ehzISlSN
&Offset=3
&Limit=2
&BeginTime=9
&EndTime=8
```

### 响应示例
    
```json
{
  "Action": "GetUSAIpAtkBriefEventsResponse",
  "AtkEvents": [
    {
      "AtkPeakBps": "169.89",
      "AtkPeakPps": "2.05",
      "AtkStartTime": 1568242777,
      "AtkType": "",
      "CostTime": 1800,
      "DetailId": 1314375,
      "EventId": 3907371,
      "Ip": "45.249.247.123",
      "MoreDetail": 1,
      "PktFileUrl": "http://ddospcap.ufile.ucloud.cn/1.pcap.gz",
      "Region": 3001,
      "Type": 0
    },
    {
      "AtkPeakBps": "7598.75",
      "AtkPeakPps": "115.66",
      "AtkStartTime": 1568190138,
      "AtkType": "SYN_FLOOD",
      "CostTime": 11,
      "DetailId": 1314332,
      "EventId": 3899098,
      "Ip": "103.72.146.106",
      "MoreDetail": 1,
      "PktFileUrl": "http://ddospcap.ufile.ucloud.cn/2.pcap.gz",
      "Region": 3001,
      "Type": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 10
}
```





