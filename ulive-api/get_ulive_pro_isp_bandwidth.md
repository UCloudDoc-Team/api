# 按省份运营商获取域名带宽数据 - GetUliveProIspBandwidth

## 简介

按省份运营商获取域名带宽数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUliveProIspBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUliveProIspBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的起始日期，格式为Unix Timestamp  忽略时间部分 |**Yes**|
| **EndTime** | int | 查询的结束日期，格式为Unix Timestamp  忽略时间部分 |**Yes**|
| **Type** | int | 时间粒度3(一分钟) 0(五分钟) 1(小时) 2(天)（默认五分钟粒度） |No|
| **DomainId.N** | string | 直播加速资源ID，创建直播加速时生成的ID，可以传多个，如果不传该参数则获取用户账户下所有DomainId |No|
| **Domain.N** | string | 域名,可以传多个，如果不传该参数则获取DomainId.n资源id下的所有域名<br />注：如果只有Domain.n而没有DomainId.n的情况，会忽略Domain.n参数 |No|
| **Province.N** | string | 省份代码，可以传多个，不传则查询所有省份<br />(省份代码见最后附录) |No|
| **Isp** | string | 运营商代码，一次只能查询一个运营商，不传递默认取所有运营商<br />(运营商代码见最后附录) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthSet** | array[[*ProIspBandwidthSet*](#ProIspBandwidthSet)] | 按省份的带宽流量实例表。具体参考下面BandwidthSet |**Yes**|

#### 数据模型


#### ProIspBandwidthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Province** | string | 省份代码 |**Yes**|
| **BandwidthList** | array[[*ProIspBandwidthList*](#ProIspBandwidthList)] | 省份带宽流量实例表 |**Yes**|

#### ProIspBandwidthList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **CdnBandwidth** | float | 返回值返回指定时间区间内CDN的带宽峰值，单位Mbps |No|

## 示例

### 请求示例
    
```
http://api.ucloud.cn/?Action= GetUliveProIspBandwidth
& DomainId.0=domain-0331qd
& BeginTime=1399305600
& EndTime=1399305600
&Province.0=beijing
&Province.1=shanghai
&Isp=dianxin
&Type=8
```

### 响应示例
    
```json
{
  "Action": " GetUliveProIspBandwidthResponse",
  "BandwidthSet": [
    {
      "BandwidthList": [
        {
          "CdnBandwidth": 1058.6,
          "Time": " 1399305600"
        },
        {
          "CdnBandwidth": 1958.6,
          "Time": " 1399305900"
        },
        {
          "CdnBandwidth": 2058.6,
          "Time": " 1399306200"
        }
      ],
      "Province": "beijing "
    },
    {
      "BandwidthList": [
        {
          "CdnBandwidth": 1058.6,
          "Time": " 1399305600"
        },
        {
          "CdnBandwidth": 1958.6,
          "Time": " 1399305900"
        },
        {
          "CdnBandwidth": 2058.6,
          "Time": " 1399306200"
        }
      ],
      "Province": "shanghai"
    }
  ],
  "RetCode": 0
}
```





