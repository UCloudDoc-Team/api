# 获取域名九五峰值带宽数据【新】 - GetUcdnDomain95BandwidthV2

## 简介

获取域名九五峰值带宽数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomain95BandwidthV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomain95BandwidthV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的起始日期，格式为Unix Timestamp   |**Yes**|
| **EndTime** | int | 查询的结束日期，格式为Unix Timestamp  |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外 不填默认为全部区域 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Time** | int | 查询时间期间的95带宽时间点  Unix时间戳 |**Yes**|
| **CdnBandwidth** | float | 查询期间的CDN的95带宽值，单位Mbps |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnDomain95BandwidthV2
&ProjectId=XczGqEQp
&BeginTime=5
&EndTime=8
&DomainId.n=VqFYNgfW
&Areacode=gwlMdkcg
```

### 响应示例
    
```json
{
  "Action": "GetUcdnDomain95BandwidthV2Response",
  "BandwidthList": [
    {
      "CdnBandwidth": 8.65344,
      "Time": 6
    }
  ],
  "CdnBandwidth": 4.56228,
  "RetCode": 0
}
```





