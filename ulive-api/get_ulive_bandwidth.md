# 获取直播加速带宽 - GetUliveBandwidth

## 简介

获取直播加速带宽






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUliveBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUliveBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | int | 带宽查询粒度，0：5分钟；1：1小时；2：1天；	 3：1分钟 |**Yes**|
| **DomainId.N** | string | 域名ID，创建域名时生成的ID，不传则获取所有 |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。如没有赋值，则返回缺少参 数错误，如果没有EndTime，BeginTime也可以不赋值，EndTime默认当前时间，BeginTime 默认前一天的当前时间。 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|
| **Protocol** | string | 协议。all:查询总带宽，https：查询https带宽，other：查询非https带宽，ipv4:查询ipv4带宽，ipv6:查询ipv6带宽，默认all |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthSet** | array[[*BandwidthSet*](#BandwidthSet)] | 带宽流量实例表。 |No|
| **Traffic** | string | 从起始时间到结束时间内所使用的总流量，单位GB |No|
| **MaxBandwidth** | string | 从起始时间到结束时间内带宽峰值 |No|
| **MaxBandwidthTime** | int | 带宽峰值时间点，格式：时间戳 |No|

#### 数据模型


#### BandwidthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **Value** | string | 带宽数值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUliveBandwidth
&ProjectId=bpOUjwfl
&Type=4
&DomainId.n=UsgWxRYz
&BeginTime=7
&EndTime=6
&Protocol=iVmuKZJN
```

### 响应示例
    
```json
{
  "Action": "GetUliveBandwidthResponse",
  "BandwidthSet": [
    {
      "Time": 6,
      "Value": 5.75534
    }
  ],
  "MaxBandwidth": "pVPTEOIj",
  "MaxBandwidthTime": 1,
  "RetCode": 0,
  "Traffic": "XSfNdZgo"
}
```





