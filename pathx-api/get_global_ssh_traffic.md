# 获取GlobalSSH流量统计数据 - GetGlobalSSHTraffic

## 简介

获取GlobalSSH流量统计数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetGlobalSSHTraffic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetGlobalSSHTraffic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGAId** | string | 资源ID，如uga-as5daw |**Yes**|
| **BeginTime** | int | 查询起始时间，如1525017600 |**Yes**|
| **EndTime** | int | 查询结束时间，如1525103999 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGAId** | string | 资源ID |**Yes**|
| **DataSet** | array[[*TrafficDaily*](#TrafficDaily)] | 流量统计数据 |**Yes**|
| **TrafficDailyRecently** | array[[*TrafficDailyRecently*](#TrafficDailyRecently)] | 最近3个月日流量统计数据 |No|

#### 数据模型


#### TrafficDaily

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Date** | int | 日期 |**Yes**|
| **Traffic** | int | 流量（单位GB） |**Yes**|
| **BillingState** | string | Yes:已扣费, No:未扣费 |**Yes**|

#### TrafficDailyRecently

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Day** | string | 日期 |No|
| **TrafficUnitMB** | string | 日流量(单位MB) |No|
| **TrafficUnitGB** | string | 日流量(单位GB) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetGlobalSSHTraffic
&ProjectId=org-xxxx
&UGAId=uga-usai7d
&BeginTime=1525017600
&EndTime=1526399999
```

### 响应示例
    
```json
{
  "Action": "GetGlobalSSHTrafficResponse",
  "DataSet": [
    {
      "BillingState": "No",
      "Date": 1568304000,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568390400,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568476800,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568563200,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568649600,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568131200,
      "Traffic": 0
    },
    {
      "BillingState": "No",
      "Date": 1568217600,
      "Traffic": 0
    }
  ],
  "Message": "",
  "RetCode": 0,
  "TrafficDailyRecently": [
    {
      "Day": "uZZsUBmp",
      "TrafficUnitGB": "sJNgQpQk",
      "TrafficUnitMB": "lRVjQUCU"
    }
  ],
  "UGAId": "uga-usai7d"
}
```





