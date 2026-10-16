# 更新告警策略 - UpdateAlertStrategy

## 简介

更新告警策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateAlertStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateAlertStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **AlertStrategyID** | string | 告警策略id |**Yes**|
| **Name** | string | 告警策略名称。最大长度255个字符 |**Yes**|
| **ProductKey** | string | 产品唯一标识，参见 [产品概览](https://docs.ucloud.cn/cloudwatch/metric/intro) |**Yes**|
| **ObjectType** | int | 绑定资源类型 1 资源组 2 资源 |**Yes**|
| **ConfigMode** | int | 条件设置方式 1. 手动配置 2.选择模版 |**Yes**|
| **Resources.N** | string | 绑定资源，对应绑定资源类型ObjectType=2 |No|
| **ResourceGroupIDs.N** | int | 绑定资源组，对应绑定资源类型ObjectType=1 |No|
| **TemplateId** | int | 模板id.对应ConfigMode=2 |No|
| **RuleSet.N.MetricID** | int | 规则指标ID。参考该类型产品下返回的指标列表GetProductMetrics |No|
| **RuleSet.N.ThresholdCompare** | int | 阈值比较方式。 枚举值：<br />1：>= <br />2：<= <br />3：> <br />4：< <br />5：== <br />6：!= |No|
| **RuleSet.N.ThresholdValue** | int | 触发阈值 |No|
| **RuleSet.N.TriggerCount** | int | 触发次数<br /> |No|
| **RuleSet.N.SendPeriodType** | string | 触发周期。枚举值：continuous连续 exponent 指数 single 不重复 |No|
| **RuleSet.N.Level** | string | 告警等级。枚举值：P0,P1,P2,P3 |No|
| **RuleSet.N.Status** | int | 告警状态。枚举值：0-关闭 1-开启 |No|
| **RuleSet.N.SendInterval** | int | 沉默周期(告警周期选择为连续时必填) |No|
| **NotifyType** | string | 通知类型 通知组 group 通知人 user |No|
| **NotifyUserIDs.N** | int | 通知人id |No|
| **NotifyGroupIDs.N** | int | 通知人组id |No|
| **NotifyChannelDs.N** | string | 通知渠道 短信sms 邮件email 回调webhook |No|
| **CallbackLanguage** | string | 通知渠道回调webhook 回调语言 中文cn 英文en |No|
| **CallbackUrls.N** | string | 回调url |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*AlertStrategyId*](#AlertStrategyId) | 更新告警策略返回对象<br /> |No|

#### 数据模型


#### AlertStrategyId

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AlertStrategyID** | int | 告警策略id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateAlertStrategy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=hEDzCADE
&AlertStrategyID=wzBiMDOY
&Name=opVpXTvF
&ProductKey=guTjyfVD
&ObjectType=1
&Resources.N.0=DtMqyNEA
&ResourceGroupIDs.N.0=5
&Tags.N.key=MRpLGNPu
&Tags.N.Operator=fdgdIBeM
&Tags.N.Values.N.0=LPpcjdkb
&ConfigMode=7
&TemplateId=9
&RuleSet.N.MetricID=3
&RuleSet.N.ThresholdCompare=6
&RuleSet.N.ThresholdValue=6
&RuleSet.N.TriggerCount=3
&RuleSet.N.SendPeriodType=dISAjraT
&RuleSet.N.Level=DsGBHRkE
&RuleSet.N.Status=6
&RuleSet.N.SendInterval=1
&NotifyType=zlffquPL
&NotifyUserIDs.N.0=2
&NotifyGroupIDs.N.0=6
&NotifyChannelDs.N.0=RWRucvvn
&CallbackLanguage=NUHEQECZ
&CallbackUrls.N.0=hkLnxfjh
```

### 响应示例
    
```json
{
  "Action": "UpdateAlertStrategyResponse",
  "Data": {},
  "RetCode": 0
}
```





