# 按省份运营商获取域名带宽数据【新】 - GetUcdnProIspBandwidthV2

## 简介

按省份运营商获取域名带宽数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnProIspBandwidthV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnProIspBandwidthV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的起始日期，格式为Unix Timestamp   |**Yes**|
| **EndTime** | int | 查询的结束日期，格式为Unix Timestamp   |**Yes**|
| **Type** | int | 时间粒度<br />0 (按5分钟粒度)<br />1 (按小时粒度)<br />2(按天粒度)<br />3(按分钟粒度） |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Province.N** | string | 省份代码，可以传多个，不传则查询所有省份 |No|
| **Isp** | string | 运营商代码，一次只能查询一个运营商，不传递默认取所有运营商 |No|

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
| **BandwidthTrafficList** | array[[*ProIspBandwidthList*](#ProIspBandwidthList)] | 省份带宽流量实例表 |**Yes**|

#### ProIspBandwidthList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **CdnBandwidth** | float | 返回值返回指定时间区间内CDN的带宽峰值，单位Mbps |No|
| **Traffic** | float | 对应时间粒度的流量，单位字节 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnProIspBandwidthV2
&ProjectId=ZjPtoiWU
&BeginTime=4
&EndTime=9
&Type=6
&DomainId.n=SNEulleF
&Province.n=CqLzocHr
&Isp=uNowNygR
```

### 响应示例
    
```json
{
  "Action": "GetUcdnProIspBandwidthV2Response",
  "BandwidthSet": [
    {
      "BandwidthList": [
        {
          "CdnBandwidth": 3.79748,
          "Time": 5
        }
      ],
      "Province": "xIjRHOXf"
    }
  ],
  "RetCode": 0
}
```





