# 获取bucket每日账单 - GetUFileDailyBill

## 简介

获取bucket每日账单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileDailyBill)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileDailyBill`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartTime** | int | 查询开始时间;unix时间戳，单位s |**Yes**|
| **EndTime** | int | 查询结束时间;unix时间戳,单位s |**Yes**|
| **BucketName** | string | 空间名称。此字段不为空，返回此Bucket日账单,否则，返回这个项目的日账单 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*BucketBills*](#BucketBills)] | 消费情况 |**Yes**|

#### 数据模型


#### BucketBills

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketBills** | array[[*UFileDailyBillItem*](#UFileDailyBillItem)] |  |No|

#### UFileDailyBillItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GetCountIaBill** | float | 下载低频存储次数费用；分 |No|
| **GetCountBill** | float | 下载标准存储次数费用；分 |No|
| **PutCountAcBill** | float | 上传归档存储次数费用；分 |No|
| **PutCountIaBill** | float | 上传低频存储次数费用；分 |No|
| **PutCountBill** | float | 上传标准存储次数费用；分 |No|
| **ObjectTagCountBill** | float | 对象标签费用: 分 |No|
| **StorageBill** | float | 标准-存储总容量费用；分 |No|
| **IaStorageBill** | float | 低频-存储总容量费用；分 |No|
| **AcStorageBill** | float | 归档-存储总容量费用；分 |No|
| **IaGetSizeBill** | float | 低频-数据取回量，即低频文件的数据取回量费用；分 |No|
| **AcRestoreBill** | float | 归档-标准解冻量，即归档文件的解冻类型为标准（Strandard）的解冻量费用； 分 |No|
| **AcExpeditedRetrievalBill** | float | 归档-高优先级解冻量，即归档文件的解冻类型为高优先级（Expedited）的解冻量费用； 分 |No|
| **IaShortStorageBill** | float | 低频-短期存储量，即补足未满最短存储期限的剩余天数的存储量费用；分 |No|
| **AcShortStorageBill** | float | 归档-短期存储量，即补足未满最短存储期限的剩余天数的存储量费用；分 |No|
| **ImageHandleFlowBill** | float | 基础图片处理量费用；分 |No|
| **ImageCompressCountBill** | float | 图片高级压缩次数费用；分 |No|
| **BusyFlowBill** | float | 忙时流量费用；分；海外无此字段 |No|
| **IdleFlowBill** | float | 闲时流量费用；分；海外无此字段 |No|
| **CdnFlowBill** | float | cdn回源流量费用;分 |No|
| **FlowBill** | float | 下载流量费用：分；国内无此字段 |No|
| **Date** | int | 配额消费时间，unix时间戳；单位s，精确到日期 |No|
| **GetCountAcBill** | float | 下载归档存储次数费用；分 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileDailyBill
&Region=cn-zj
&ProjectId=UdlOdbuF
&BucketName=HGrwkMQD
&StartTime=7
&EndTime=7
```

### 响应示例
    
```json
{
  "Action": "GetUFileDailyBillResponse",
  "DataSet": [
    "AALyFfHn"
  ],
  "RetCode": 0
}
```





