# 获取bucket月度账单 - GetUFileMonthlyBill

## 简介

获取bucket月度账单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUFileMonthlyBill)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUFileMonthlyBill`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StartMonth** | string | 查询开始月份;例如"1994-07" |**Yes**|
| **EndMonth** | string | 查询结束时间;例如"1994-07" |**Yes**|
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
| **BucketBills** | array[[*UFileMonthlyBillItem*](#UFileMonthlyBillItem)] | bucket账单 |No|

#### UFileMonthlyBillItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Labels** | array[[*BucketLabels*](#BucketLabels)] | bucket对应的资源系统标签 |No|
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
| **Month** | string | 配额消费月份 |No|
| **GetCountAcBill** | float | 下载归档存储次数费用；分 |No|
| **TotalBill** | float | 总费用;分 |No|

#### BucketLabels

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 标签对应key |No|
| **Value** | string | 标签对应value |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUFileMonthlyBill
&Region=cn-zj
&ProjectId=wwczmFmD
&StartTime=7
&EndTime=8
&BucketName=nkGlQMSE
```

### 响应示例
    
```json
{
  "Action": "GetUFileMonthlyBillResponse",
  "DataSet": [
    {
      "BucketBills": [
        {
          "AcExpeditedRetrievalBill": 9.96545,
          "AcRestoreBill": 3.14862,
          "AcShortStorageBill": 6.15971,
          "AcStorageBill": 7.52229,
          "BusyFlowBill": 8.55265,
          "CdnFlowBill": 6.33826,
          "Date": 1,
          "FlowBill": 4.21449,
          "GetCountAcBill": 1.68791,
          "GetCountBill": 7.85645,
          "GetCountIaBill": 2.97784,
          "IaGetSizeBill": 6.13791,
          "IaShortStorageBill": 8.98736,
          "IaStorageBill": 1.68397,
          "IdleFlowBill": 2.14974,
          "ImageCompressCountBill": 3.95593,
          "ImageHandleFlowBill": 9.57945,
          "Labels": [
            {
              "Key": "pIydtLYh",
              "Value": "NpGlhTNv"
            }
          ],
          "ObjectTagCountBill": 8.89374,
          "PutCountAcBill": 5.95617,
          "PutCountBill": 4.61413,
          "PutCountIaBill": 3.68122,
          "StorageBill": 5.13637,
          "TotalBill": 4.52664
        }
      ]
    }
  ],
  "RetCode": 0
}
```





