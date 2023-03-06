# 查看日消费报表 - GetUFileDailyReport

## 简介

查看日消费报表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileDailyReport)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileDailyReport`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | int | 查询开始时间;unix时间戳，单位s |**Yes**|
| **EndTime** | int | 查询结束时间;unix时间戳,单位s |**Yes**|
| **BucketName** | string | 空间名称。此字段不为空，返回此Bucket日使用量；否则，返回这个项目的日使用量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileReportItem*](#UFileReportItem)] | 消费情况 |**Yes**|

#### 数据模型


#### UFileReportItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | array[[*UFileTotalReportItem*](#UFileTotalReportItem)] | 总消费情况 |No|
| **Daily** | array[[*UFileDailyReportItem*](#UFileDailyReportItem)] | 日消费情况 |No|

#### UFileTotalReportItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Flow** | float | 下载流量：单位GB；国内无此字段 |No|
| **IdleFlow** | float | 闲时流量；单位GB；海外无此字段 |No|
| **BusyFlow** | float | 忙时流量；单位GB；海外无此字段 |No|
| **CdnFlow** | float | cdn回源流量;单位GB |No|
| **ApiTimes** | float | API请求次数（万次） |No|

#### UFileDailyReportItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Storage** | float | 标准存储量；单位GB |No|
| **IaStorage** | float | 低频存储量；单位GB |No|
| **AcStorage** | float | 冷存（归档）存储量；单位GB |No|
| **IaGetSize** | float | 低频数据取回量；单位GB |No|
| **AcRestore** | float | 冷存激活量，即归档数据取回量；单位GB |No|
| **BusyFlow** | float | 忙时流量；单位GB；海外无此字段 |No|
| **IdleFlow** | float | 闲时流量；单位GB；海外无此字段 |No|
| **CdnFlow** | float | cdn回源流量;单位GB |No|
| **Flow** | float | 下载流量：单位GB；国内无此字段 |No|
| **Date** | int | 配额消费时间，unix时间戳（单位s），精确到日期 |No|
| **ApiTimes** | float | API请求次数（万次） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileDailyReport
&Region=cn-zj
&ProjectId=hKcUXqkX
&StartTime=4
&EndTime=7
&Bucket=vdXesnhh
```

### 响应示例
    
```json
{
  "Action": "GetUFileDailyReportResponse",
  "RetCode": 0
}
```





