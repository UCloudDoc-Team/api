# 获取模板发送统计数据 - GetUSMSTemplateSendStatistics

## 简介

获取模板发送统计数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUSMSTemplateSendStatistics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSMSTemplateSendStatistics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Page** | int | 页编号，从0开始 |**Yes**|
| **NumPerPage** | int | 每页记录个数 |**Yes**|
| **OrderBy** | string | 排序字段，如BrevityCode表示按照BrevityCode排列，配合OrderType使用。目前支持SendDate、BrevityCode |**Yes**|
| **OrderType** | string | 排序方式，asc-正序 desc-倒序 |**Yes**|
| **StartDate** | string | 开始日期，格式为YYYY-MM-DD |**Yes**|
| **EndDate** | string | 结束日期，格式为YYYY-MM-DD |**Yes**|
| **Domestic** | int | 国内标记，0-国际短信 1-国内短信 |**Yes**|
| **BrevityCode** | string | 国际简码，如CN表示中国，当需要查询多个国家时，使用-分割，如CN-ID。 |No|
| **TemplateId** | string | 短信模板ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Total** | int | 返回记录数 |**Yes**|
| **StatisticsData** | [*StatisticsData*](#StatisticsData) | 符合查询条件的发送数据统计求和集，具体字段信息见StatisticsData模型 |**Yes**|
| **Data** | array[[*TemplateStatisticsDataInfo*](#TemplateStatisticsDataInfo)] | 以天为统计维度的发送数据统计集合，每天的统计数据字段详见TemplateStatisticsDataInfo模型 |No|

#### 数据模型


#### StatisticsData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UnknownCount** | int | 状态未知数（提交条数） |**Yes**|
| **SuccessCount** | int | 发送成功数（提交条数） |**Yes**|
| **SendCostCount** | int | 发送总数（拆分条数） |**Yes**|
| **FailCount** | int | 发送失败数（提交条数） |**Yes**|
| **SendCount** | int | 发送总数（提交条数） |**Yes**|
| **SuccessCostCount** | int | 发送成功数（拆分条数） |**Yes**|
| **FailCostCount** | int | 发送失败数（拆分条数） |**Yes**|
| **UnknownCostCount** | int | 状态未知数（拆分条数） |**Yes**|
| **SubmitFailCount** | int | 提交失败数（提交条数） |**Yes**|
| **SubmitFailCostCount** | int | 提交失败数（拆分条数） |**Yes**|

#### TemplateStatisticsDataInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SendDate** | string | 发送时间 |**Yes**|
| **BrevityCode** | string | 国际/地区标识码 |**Yes**|
| **TemplateId** | string | 短信模板ID |**Yes**|
| **Count** | int | 发送总数（提交条数） |**Yes**|
| **CostCount** | int | 发送总数（拆分条数） |**Yes**|
| **SuccessCount** | int | 发送成功数（提交条数） |**Yes**|
| **SuccessCostCount** | int | 发送成功数（拆分条数） |**Yes**|
| **FailedCount** | int | 发送失败数（提交条数） |**Yes**|
| **FailedCostCount** | int | 发送失败数（拆分条数） |**Yes**|
| **UnknownCount** | int | 状态未知数（提交条数） |**Yes**|
| **UnknownCostCount** | int | 状态未知数（拆分条数） |**Yes**|
| **SubmitFailedCount** | int | 提交失败数（提交条数） |**Yes**|
| **SubmitFailedCostCount** | int | 提交失败数（拆分条数） |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSMSTemplateSendStatistics
&ProjectId=NisAYPmv
&Page=5
&NumPerPage=5
&OrderBy=jOdlouXH
&OrderType=umirvnPn
&StartDate=pkwNCtsO
&EndDate=fOEqzdNm
&Domestic=5
&BrevityCode=sXFqlpJN
&TemplateId=frUFWoVs
```

### 响应示例
    
```json
{
  "Action": "GetUSMSTemplateSendStatisticsResponse",
  "Data": [
    {
      "BrevityCode": "kbBFlxEg",
      "CostCount": 1,
      "Count": 9,
      "FailedCostCount": 3,
      "FailedCount": 7,
      "SendDate": "aGQopQIl",
      "SubmitFailedCostCount": 1,
      "SubmitFailedCount": 7,
      "SuccessCostCount": 4,
      "SuccessCount": 4,
      "TemplateId": "JelSfPNU",
      "UnknownCostCount": 6,
      "UnknownCount": 3
    }
  ],
  "Message": "iCneNUGy",
  "RetCode": 0,
  "StatisticsData": {},
  "Total": 2
}
```





