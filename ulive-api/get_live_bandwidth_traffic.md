# 获取直播域名带宽流量(新系统) - GetLiveBandwidthTraffic

## 简介

获取直播域名带宽流量(新系统)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetLiveBandwidthTraffic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetLiveBandwidthTraffic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 查询流量的起始时间，格式：Unix时间戳 |**Yes**|
| **EndTime** | string | 查询流量的结束时间，格式：Unix时间戳 |**Yes**|
| **Domain.N** | string | 域名,可以传多个，如果不传该参数则获取用户账户的总带宽，n为自然数多个Domain的你不相同，表示多个域名 |No|
| **Granularity** | string | 时间粒度，onemin:1分钟 fivemin：5分钟 hour:小时 ，day：天<br />默认5分钟，1分钟粒度只能获取一天的数据，其他粒度的数据最多获取31天的数据 |No|
| **Sum** | int | 是否汇总：1=是 0=否  默认是, 汇总返回的域名字段值sum |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthSet** | array[[*DomainBandwidthInfo*](#DomainBandwidthInfo)] | 域名带宽流量实例表。具体参考下面DomainBandwidthInfo |**Yes**|

#### 数据模型


#### DomainBandwidthInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名,指定Sum参数为1的情况下，值为 "sum" |No|
| **BandwidthList** | string | 带宽流量实例表。具体参考下面BandwidthInfo |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetLiveBandwidthTraffic
&ProjectId=lWgkYZyd
&BeginTime=7
&EndTime=LgABRXlH
&Domain.n=ViqyXzRX
&Granularity=vSNZhVIR
&Sum=1
```

### 响应示例
    
```json
{
  "Action": "GetLiveBandwidthTrafficResponse",
  "BandwidthSet": [
    {
      "BandwidthList": [
        {
          "Bandwidth": 2.24644,
          "Time": 2,
          "Traffic": 8.42461
        }
      ],
      "Domain": "cOPypIiZ"
    }
  ],
  "RetCode": 0
}
```





