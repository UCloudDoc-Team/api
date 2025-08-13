# 告警记录 - ListAlertRecord

## 简介

获取时间段内的告警记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListAlertRecord)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListAlertRecord`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 |**Yes**|
| **StartAt** | int | 开始时间，查询告警记录开始时间(不支持查询距当前时间一年前的数据) |**Yes**|
| **EndAt** | int | 结束时间，查询告警记录结束时间(查询开始时间和结束时间不能超过一个月) |**Yes**|
| **Fuzzy** | string | 模糊查询(支持资源id模糊搜索) |No|
| **Filter.ProductTypes.N** | int | 产品类型，根据产品类型精确搜索对应的告警记录 |No|
| **Filter.Levels.N** | string | 告警级别，根据告警级别精确搜索对应的告警记录 |No|
| **Filter.Status.N** | string | 告警状态，根据告警状态精确搜索对应的告警记录 |No|
| **OrderType** | string | 排序(默认根据告警发生时间倒序) |No|
| **Limit** | int | 查询返回数量，默认值300，最大值：300。<br /> |No|
| **Offset** | int | 数据偏移量 (默认0)<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*AlertRecord*](#AlertRecord)] | 告警记录集合 |No|
| **TotalCount** | int | 告警记录总数 |No|

#### 数据模型


#### AlertRecord

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 可用区 |No|
| **RecordID** | int | 告警记录RecordID |No|
| **ProjectID** | int | 项目ProjectID |No|
| **StrategyName** | string | 告警记录触发告警策略名称 |No|
| **ProductType** | int | 产品类型 |No|
| **ProductName** | string | 产品类型名称 |No|
| **ResourceID** | string | 资源id |No|
| **MetricID** | int | 指标id |No|
| **MetricName** | string | 指标名称 |No|
| **UnitName** | string | 指标单位名称 |No|
| **StrategyID** | int | 告警记录触发告警策略Id |No|
| **RuleID** | int | 告警记录触发告警规则Id |No|
| **Tag** | array[string] | 告警点tag信息 |No|
| **Value** | int | 告警当前值 |No|
| **ThresholdCompare** | int | 比较符 |No|
| **ThresholdValue** | int | 告警阈值 |No|
| **ShieldRuleID** | int | 告警屏蔽规则id(如果配置了屏蔽规则，并且满足条件) |No|
| **Level** | string | 告警等级 |No|
| **Status** | string | 告警状态 |No|
| **StartAt** | int | 告警触发时间 |No|
| **EndAt** | int | 告警恢复时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListAlertRecord
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lHbpbCJv
&RecordID=1
&StartAt=4
&EndAt=7
&Fuzzy=hAVEfaDE
&RecordID=6
&StartAt=5
&EndAt=8
&Fuzzy=jVymouaW
&Fuzzy=WYjEKfyo
&Filter.ProductTypes.N=6
&Filter.Levels.N=lxexxlZh
&Filter.Status.N=wakzNxlZ
&OrderType=JXKKXtZY
&Limit=3
&Offset=3
```

### 响应示例
    
```json
{
  "Action": "ListAlertRecordResponse",
  "Data": [
    "pnYwysIe"
  ],
  "RetCode": 0,
  "TotalCount": 6
}
```





