# 查看存储桶日消费报表 - GetUFileBucketDailyReport

## 简介

查看存储桶日消费报表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileBucketDailyReport)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileBucketDailyReport`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | int | 查询开始时间;unix时间戳，单位s |**Yes**|
| **EndTime** | int | 查询结束时间;unix时间戳，单位s |**Yes**|
| **BucketName** | string | 存储空间名称。 |**Yes**|

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
| **Flow** | float | 下载流量：单位byte；国内无此字段 |No|
| **IdleFlow** | float | 闲时流量；单位byte；海外无此字段 |No|
| **BusyFlow** | float | 忙时流量；单位byte；海外无此字段 |No|
| **CdnFlow** | float | cdn回源流量;单位byte |No|
| **ApiTimes** | float | API请求次数（次） |No|

#### UFileDailyReportItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Storage** | float | 标准存储量；单位byte |No|
| **IaStorage** | float | 低频存储量；单位byte |No|
| **AcStorage** | float | 冷存（归档）存储量；单位byte |No|
| **IaGetSize** | float | 低频数据取回量；单位byte |No|
| **AcRestore** | float | 冷存激活量，即归档数据取回量；单位byte |No|
| **BusyFlow** | float | 忙时流量；单位byte；海外无此字段 |No|
| **IdleFlow** | float | 闲时流量；单位byte；海外无此字段 |No|
| **CdnFlow** | float | cdn回源流量;单位byte |No|
| **Flow** | float | 下载流量：单位byte；国内无此字段 |No|
| **Date** | int | 配额消费时间，unix时间戳（单位s），精确到日期 |No|
| **ApiTimes** | float | API请求次数（次） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileBucketDailyReport
&Region=cn-zj
&ProjectId=JahMXKHs
&StartTime=4
&EndTime=2
&BucketName=boxpcxsj
```

### 响应示例
    
```json
{
  "Action": "GetUFileBucketDailyReportResponse",
  "DataSet": [
    {
      "Daily": [
        {
          "AcRestore": 4.19936,
          "AcStorage": 7.91188,
          "ApiTimes": 8.25335,
          "BusyFlow": 5.81338,
          "CdnFlow": 9.65715,
          "Date": 9,
          "Flow": 9.75386,
          "IaGetSize": 7.15271,
          "IaStorage": 4.13334,
          "IdleFlow": 4.37315,
          "Storage": 1.34855
        }
      ],
      "Total": [
        {
          "ApiTimes": 2.42724,
          "BusyFlow": 4.57755,
          "CdnFlow": 8.58523,
          "Flow": 1.27244,
          "IdleFlow": 2.77132
        }
      ]
    }
  ],
  "RetCode": 0
}
```





