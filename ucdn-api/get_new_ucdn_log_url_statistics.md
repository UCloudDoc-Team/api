# 获取日志url统计 - GetNewUcdnLogUrlStatistics

## 简介

获取日志url统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnLogUrlStatistics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnLogUrlStatistics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DomainId** | string | 域名Id |**Yes**|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外 只支持国内 |No|
| **BeginTime** | int | 查询带宽的起始时间，格式：时间戳。BeginTime和EndTime必须同时赋值 |No|
| **EndTime** | int | 查询统计日志的结束时间，格式：时间戳,最多可拉取30天 |No|
| **OrderBy** | int | 0表示按流量降序排列，1表示按照下载次数降序排列，默认为0 |No|
| **Limit** | int | 返回的结果数量限制，默认1000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UrlStatisticsList** | array[[*UrlStatistics*](#UrlStatistics)] | 按天统计实例。 |No|

#### 数据模型


#### UrlStatistics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UrlList** | array[[*DownloadStatisticInfo*](#DownloadStatisticInfo)] |  |No|
| **Date** | string | 日期 |No|

#### DownloadStatisticInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Url** | string | 下载链接的url |No|
| **Traffic** | float | 流量（单位为G） |No|
| **DownloadTimes** | int | 下载次数 |No|
| **Percent** | float | 流量占比，单位% |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnLogUrlStatistics
&ProjectId=KaStjefE
&DomainId=apVismjF
&Areacode=MvvZFjqG
&BeginTime=9
&EndTime=2
&OrderBy=8
&Limit=6
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnLogUrlStatisticsResponse",
  "LogStatisticsList": [
    {
      "Date": "xoeJcpan",
      "UrlList": [
        {
          "DownloadTimes": 4,
          "Percent": 3.61651,
          "Traffic": 1.63161,
          "Url": "LeiDBXkN"
        }
      ]
    }
  ],
  "RetCode": 0
}
```





