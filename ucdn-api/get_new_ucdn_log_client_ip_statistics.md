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
| **BeginTime** | int | 查询的日期，单位：Unix时间戳。只支持按天查询 |No|
| **OrderBy** | int | 0表示按照下载次数降序排列，1表示按流量降序排列，默认为0 |No|
| **Limit** | string | 返回结果数量限制，返回最多100条 |No|
| **Type** | int | 1表示按照1小时粒度，2表示按照一天的粒度 默认是天 |No|

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
| **Flow** | int | 流量单位字节 |No|
| **IP** | string | 客户端IP |No|
| **Requst** | int | 请求数 |No|
| **FlowPercent** | float | 流量占比 |No|
| **RequestPercent** | float | 请求数占比 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnLogClientIpStatistics
&ProjectId=SIDfHYdh
&DomainId=wsIHivpj
&Areacode=dAFzdmyj
&BeginTime=2
&EndTime=4
&OrderBy=3
&Limit=xNEJXPBv
&Type=4
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnLogClientIpStatisticsResponse",
  "ClientIpStatisticsList": [
    {
      "Flow": 6,
      "FlowPercent": 2.21938,
      "IP": "hByeMlQr",
      "RequestPercent": 8.52443,
      "Requst": 7
    }
  ],
  "RetCode": 0
}
```





