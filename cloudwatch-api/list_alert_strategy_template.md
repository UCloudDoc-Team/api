# 条件模板列表 - ListAlertStrategyTemplate

## 简介

条件模板列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListAlertStrategyTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListAlertStrategyTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考GetProjectList接口	 |**Yes**|
| **TemplateIDs.N** | int | 模板id集合，根据模板id获取告警条件模板列表 |No|
| **Limit** | int | 查询返回数量，默认值300，最大值：300。 |No|
| **Offset** | int | 数据偏移量 (默认0) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ListAlertTemplate*](#ListAlertTemplate)] | 条件模板列表 |No|
| **TotalCount** | int | 条件模板总条数 |No|

#### 数据模型


#### ListAlertTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CompanyID** | int | 公司id |No|
| **TemplateID** | int | 模板Id |No|
| **Name** | string | 告警模板名称 |No|
| **ProductType** | int | 产品类型(数值型)。参考ListMonitorProduct获取监控对象类型列表 |No|
| **ProductKey** | string | 产品类型(字符型)。参考ListMonitorProduct获取监控对象类型列表 |No|
| **RuleSet** | array[[*AlertRule*](#AlertRule)] | 告警条件规则 |No|
| **Remark** | string | 条件模板备注 |No|

#### AlertRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleID** | int | 规则ID |No|
| **MetricID** | int | 规则指标ID。参考该类型产品下返回的指标列表GetProductMetrics |No|
| **MetricName** | string | 指标名称 |No|
| **ThresholdCompare** | int | 阈值比较方式<br />枚举值比较方式:<br />1->=<br />2-<=<br />3-><br />4-<<br />5-==<br />6-!= |No|
| **ThresholdValue** | float | 触发阈值 |No|
| **TriggerCount** | int | 触发次数 |No|
| **SendPeriodType** | string | 触发周期。枚举值：continuous连续 exponent 指数 single 不重复 |No|
| **SendInterval** | int | 发送间隔 |No|
| **Level** | string | 告警等级。枚举值：P0,P1,P2,P3 |No|
| **Status** | int | 告警状态。枚举值：0-关闭 1-开启 |No|
| **UnitID** | int | 单位id |No|
| **UnitName** | string | 单位名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListAlertStrategyTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=WlvKlnLL
&ProjectId=kaGOEwqa
&Filter.TemplateIDs.N=8
&Limit=9
&Offset=7
```

### 响应示例
    
```json
{
  "Action": "ListAlertStrategyTemplateResponse",
  "Data": [
    {
      "CompanyID": 4,
      "Name": "dnJZlrWA",
      "ProductKey": "RwmwuAAp",
      "ProductType": 9,
      "Remark": "tNWQKTXr",
      "RuleSet": [
        {
          "Level": "cQBWjaRy",
          "MetricID": 3,
          "MetricName": "HbmMUMkx",
          "RuleID": 7,
          "SendInterval": 2,
          "SendPeriodType": "rUXdydLC",
          "Status": 3,
          "ThresholdCompare": 1,
          "ThresholdValue": 1.86358,
          "TriggerCount": 8
        }
      ],
      "TemplateID": 9
    }
  ],
  "Message": "uIxKeOnd",
  "RetCode": 0,
  "TotalCount": 6
}
```





