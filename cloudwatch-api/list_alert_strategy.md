# 获取告警策略列表 - ListAlertStrategy

## 简介

获取告警策略列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListAlertStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListAlertStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Fuzzy** | string | 模糊查询(支持告警策略名称模糊搜索)<br /> |No|
| **Filter.ProductTypes.N** | int | 产品ID，参见 [产品概览]<br />（https://docs.ucloud.cn/cloudwatch/metric/intro） |No|
| **Filter.AlertStrategyIDs.N** | int | 告警策略id，根据策略id获取告警策略列表 |No|
| **Filter.Status.N** | int | 告警策略状态，根据告警策略状态精确搜索对应的告警策略，枚举值：0-停用，1-启用<br /> |No|
| **Resources.N** | string | 资源id集合,根据资源id返回绑定的告警策略列表 |No|
| **Limit** | int | 查询返回数量，默认值300，最大值：300。<br /> |No|
| **Offset** | int | 数据偏移量 (默认0)<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*AlertStrategy*](#AlertStrategy)] | 告警策略集合 |No|
| **TotalCount** | int | 告警策略总数 |No|
| **TraceId** | string | 链路ID |No|

#### 数据模型


#### AlertStrategy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleSet** | array[[*AlertRule*](#AlertRule)] | 告警规则集合 |No|
| **AlertStrategyID** | int | 告警策略Id |No|
| **Name** | string | 告警策略名称 |No|
| **ProductType** | int | 资源类型 |No|
| **ProductKey** | string | 资源类型名称 |No|
| **ConfigMode** | int | 告警规则配置类型(基于模板配置、基于手工配置) |No|
| **TemplateId** | int | 模板Id |No|
| **NotifyType** | string | 通知方式(通知组：group，通知人：user) |No|
| **NotifyUserIDs** | array[int] | 通知人用户id集合 |No|
| **NotifyGroupIDs** | array[int] | 通知组id集合 |No|
| **NotifyChannelDs** | array[string] | 通知渠道('email', 'sms', 'webhook') |No|
| **CallbackLanguage** | string | 回调语言(cn,en) |No|
| **CallbackUrls** | array[string] | 回调地址 |No|
| **Status** | int | 告警策略状态 |No|
| **Remark** | string | 告警策略备注 |No|
| **CreatedBy** | string | 创建人 |No|
| **UpdatedBy** | string | 更新人 |No|
| **CreatedAt** | int | 创建时间 |No|
| **UpdatedAt** | int | 更新时间 |No|

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
https://api.ucloud.cn/?Action=ListAlertStrategy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tDITIKFv
&Fuzzy=lDkAENja
&Filter.ProductTypes.N=9
&Filter.Status.N=5
&Limit=7
&Offset=3
&Resources.N=DuWSrHhi
&Filter.AlertStrategyIDs.N=7
```

### 响应示例
    
```json
{
  "Action": "ListAlertStrategyResponse",
  "Data": [
    {
      "AlertStrategyID": 111,
      "CallbackLanguage": "cn",
      "CallbackUrls": [
        "https://www.test.com/callback"
      ],
      "CompanyID": 111,
      "ConfigMode": 1,
      "CreatedAt": 1755104421,
      "CreatedBy": "creator@test.com",
      "Name": "资源组告警",
      "NotifyChannelDs": [
        "webhook"
      ],
      "NotifyGroupIDs": [],
      "NotifyType": "group",
      "NotifyUserIDs": [],
      "ObjectType": 2,
      "ProductKey": "uhost",
      "ProductType": 1,
      "ProjectID": 12333,
      "Remark": "",
      "ResourceGroupIDs": [],
      "Resources": [],
      "RuleSet": [
        {
          "Level": "P2",
          "MetricID": 123312,
          "MetricName": "CPU使用率",
          "RuleID": 2223,
          "SendInterval": 2,
          "SendPeriodType": "continuous",
          "Status": 1,
          "ThresholdCompare": 1,
          "ThresholdValue": 0,
          "TriggerCount": 1,
          "UnitID": 32,
          "UnitName": "%"
        }
      ],
      "Status": 0,
      "StrategyType": 1,
      "Tags": [],
      "TemplateId": 0,
      "UpdatedAt": 1755142910,
      "UpdatedBy": "creator@test.com"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1,
  "TraceId": "a1c26582-571a-49db-a841-d4b738472008"
}
```





