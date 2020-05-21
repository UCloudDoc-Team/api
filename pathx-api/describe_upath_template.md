# 查询UPath的监控模板 - DescribeUPathTemplate

## 简介

查询UPath的监控模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUPathTemplate)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPathTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UPathId** | string | 加速线路实例ID,格式 upath-xxxx |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*AlarmRuler*](#AlarmRuler)] | 监控模板详情 |**Yes**|

#### 数据模型


#### AlarmRuler

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AlarmStrategy** | string | 收敛策略，可选范围 ['Exponential','Continuous','Once']，分别对应指数递增、连续告警、单次告警 |**Yes**|
| **AlarmFrequency** | int | 告警探测周期，单位秒 |**Yes**|
| **Compare** | string | 比较策略，可选 ['GE','LE']  分别代表不小于和不大于 |**Yes**|
| **ContactGroupId** | int | 联系组ID |**Yes**|
| **MetricName** | string | 告警指标名称, 所有n的个数必须一致。目前仅允许以下四项：UpathNetworkOut:出向带宽，UpathNetworkIn:入向带宽，UpathNetworkOutUsage:出向带宽使用率，UpathNetworkInUsage:入向带宽使用率 |**Yes**|
| **Threshold** | int | 告警阈值，带宽使用率的阈值范围是[50,100]的正整数，带宽告警阈值为1000000的倍数, 如大于2Mbps则告警 阈值应该传 2000000 |**Yes**|
| **TriggerCount** | int | 告警触发周期（次数） |**Yes**|
| **AlarmTemplateRuleId** | string | 告警模板策略ID |**Yes**|
| **ResourceType** | string | 资源类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPathTemplate
&ProjectId=org-xxxx
&UPathId=upath-xxxx
```

### 响应示例
    
```json
{
  "Action": "DescribeUPathTemplateResponse",
  "DataSet": [
    {
      "AlarmFrequency": 0,
      "AlarmStrategy": "Exponential",
      "AlarmTemplateRuleId": 19733,
      "Compare": "GE",
      "ContactGroupId": 106696,
      "MetricName": "UpathNetworkIn",
      "ResourceType": "upath",
      "Threshold": 10000000,
      "TriggerCount": 3
    },
    {
      "AlarmFrequency": 0,
      "AlarmStrategy": "Exponential",
      "AlarmTemplateRuleId": 19734,
      "Compare": "GE",
      "ContactGroupId": 106696,
      "MetricName": "UpathNetworkOut",
      "ResourceType": "upath",
      "Threshold": 10000000,
      "TriggerCount": 3
    }
  ],
  "Message": "",
  "RetCode": 0
}
```





