# 创建告警策略 - CreateAlertStrategy

## 简介

创建告警策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateAlertStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateAlertStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 告警策略名称。最大长度255个字符 |**Yes**|
| **ProductKey** | string | 产品类型。参考ListMonitorProduct获取监控对象类型列表 |**Yes**|
| **ObjectType** | int | 绑定资源类型<br /> 1 资源组 2 资源 |**Yes**|
| **ConfigMode** | int | 条件设置方式<br />1. 手动配置 2.选择模版 |**Yes**|
| **Resources.N** | string | 绑定资源，对应绑定资源类型ObjectType=2 |No|
| **ResourceGroupIDs.N** | int | 绑定资源组，对应绑定资源类型ObjectType=1 |No|
| **Tags.N.Key** | string | 数据点tag key |No|
| **Tags.N.Operator** | string | 数据点tag operator<br />包含= 不包含!= |No|
| **Values.N** | string | 数据点tag value |No|
| **TemplateId** | int | 模板id.对应TemplateId=2 |No|
| **RuleSet.N.MetricID** | int | 规则指标ID。参考该类型产品下返回的指标列表GetProductMetrics |No|
| **RuleSet.N.ThresholdCompare** | int | 阈值比较方式。 枚举值比较方式: 1->= 2-<= 3-> 4-< 5-== 6-!= |No|
| **RuleSet.N.ThresholdValue** | int | 触发阈值 |No|
| **RuleSet.N.TriggerCount** | int | 触发次数 |No|
| **RuleSet.N.SendPeriodType** | string | 触发周期。枚举值：continuous连续 exponent 指数 single 不重复 |No|
| **RuleSet.N.Level** | string | 告警等级。枚举值：P0,P1,P2,P3 |No|
| **RuleSet.N.Status** | int | 告警状态。枚举值：0-关闭 1-开启 |No|
| **RuleSet.N.SendInterval** | int | 沉默周期(告警周期选择为连续时必填) |No|
| **NotifyType** | string | 通知类型<br />通知组 group 通知人 user |No|
| **NotifyUserIDs.N** | int | 通知人id |No|
| **NotifyGroupIDs.N** | int | 通知人组id |No|
| **NotifyChannelDs.N** | string | 通知渠道<br />短信sms 邮件email 回调webhook |No|
| **CallbackLanguage** | string | 通知渠道回调webhook<br />回调语言<br />中文cn 英文en |No|
| **CallbackUrls.N** | string | 回调语言url |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*AlertStrategyId*](#AlertStrategyId) | 创建告警策略返回对象 |No|

#### 数据模型


#### AlertStrategyId

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AlertStrategyID** | int | 告警策略id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateAlertStrategy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wQzVpMKH
&Name=aMtbGsoi
&ProductKey=aimMEstF
&ObjectType=cVlUqdlo
&Name=CEyaaxRn
&ProductKey=cMfAOPHv
&ObjectType=qIlyxnMl
&Resources=GHMEDxZd
&ResourceGroupIDs=NtMeYivb
&Tags=gAUnBrer
&ConfigMode=shiTfGjt
&TemplateId=ejKhnjxe
&RuleSet=RLErYqsa
&NotifyType=YpYuSZaR
&NotifyUserIDs=GmJRfOnL
&NotifyGroupIDs=sDkHomlx
&NotifyChannelDs=vcqcBLDy
&CallbackLanguage=WjVxebho
&CallbackUrls=JpBIGAiC
&Tags.N.Operator=iIvLyhfR
&Tags.N.Values.N.0=dvkInIoI
&RuleSet.N.ThresholdCompare=7
&RuleSet.N.ThresholdValue=7
&RuleSet.N.TriggerCount=2
&RuleSet.N.SendPeriodType=QpKiRoKU
&RuleSet.N.Level=jFTScowr
&RuleSet.N.Status=8
&RuleSet.N.SendInterval=2
```

### 响应示例
    
```json
{
  "Action": "CreateAlertStrategyResponse",
  "Data": {},
  "RetCode": 0
}
```





