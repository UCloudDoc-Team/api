# 获取日志客户端ip统计 - GetNewUcdnLogClientIpStatistics

## 简介

获取日志客户端ip统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnLogClientIpStatistics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnLogClientIpStatistics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DomainId** | string | 域名id，创建域名时生成的id |**Yes**|
| **Areacode** | string | 流量统计区域 cn代表国内 abroad代表海外 ；目前只支持国内 |No|
| **BeginTime** | int | 查询的开始时间，如果有EndTime，BeginTime必须赋值。如果没有EndTime，BeginTime也可以不赋值，EndTime默认当天，BeginTime 默认前一天。 |No|
| **EndTime** | int | 查询的结束时间，格式：时间戳。EndTime默认为当天，BeginTime默认为前一天；最大支持30天 |No|
| **OrderBy** | int | 0表示按照下载次数降序排列，1表示按流量降序排列，默认为0 |No|
| **Limit** | string | 返回结果数量限制，默认1000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClientIpStatisticsList** | array[[*ClientIpStatisticsList*](#ClientIpStatisticsList)] | 客户端ip数据集合。 |No|

#### 数据模型


#### ClientIpStatisticsList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClientIpList** | array[[*ClientIpList*](#ClientIpList)] | 客户端ip数据集合。 |No|
| **Date** | string | 按日期返回格式如：2017-02-13 |No|

#### ClientIpList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | 客户端ip |No|
| **RequestNum** | int | 访问次数 |No|
| **Flow** | float | 访问流量，单位G |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnLogClientIpStatistics
&DomainId=test.com
&Areacode=cn
&BeginTime=1620057600
&EndTime=1620077600
&Limit=100
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnLogClientIpStatisticsResponse",
  "ClientIpStatisticsList": [
    {
      "ClientIpList": [
        {
          "Flow": 1.15554,
          "IP": "grOHkIEF",
          "RequestNum": 7
        },
        {
          "Flow": 8.24256,
          "IP": "urnbAaOv",
          "RequestNum": 5
        },
        {
          "Flow": 7.45337,
          "IP": "jgFUfMNd",
          "RequestNum": 5
        },
        {
          "Flow": 2.82426,
          "IP": "IYubMPot",
          "RequestNum": 7
        },
        {
          "Flow": 4.93751,
          "IP": "PehEGkoA",
          "RequestNum": 8
        },
        {
          "Flow": 7.88547,
          "IP": "USEEixMx",
          "RequestNum": 7
        },
        {
          "Flow": 2.88897,
          "IP": "znxZmsEn",
          "RequestNum": 8
        },
        {
          "Flow": 6.98333,
          "IP": "qhzPpLeg",
          "RequestNum": 9
        },
        {
          "Flow": 6.71646,
          "IP": "skRWEREI",
          "RequestNum": 6
        }
      ],
      "Date": "QZDeBGkp"
    },
    {
      "ClientIpList": [
        {
          "Flow": 6.83778,
          "IP": "zZhpZfiq",
          "RequestNum": 6
        },
        {
          "Flow": 7.68661,
          "IP": "TZTHXYIr",
          "RequestNum": 1
        }
      ],
      "Date": "UocEGyNC"
    }
  ],
  "RetCode": 0
}
```





