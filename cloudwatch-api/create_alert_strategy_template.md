# 新建条件模板 - CreateAlertStrategyTemplate

## 简介

新建条件模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateAlertStrategyTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateAlertStrategyTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 告警模板名称。最大长度64个字符 |**Yes**|
| **ProductKey** | string | 产品唯一标识，参见 [产品概览]<br />（https://docs.ucloud.cn/cloudwatch/metric/intro） |**Yes**|
| **RuleSet.N.MetricID** | int | 规则指标ID。参考该类型产品下返回的指标列表GetProductMetrics |**Yes**|
| **RuleSet.N.ThresholdCompare** | int | 阈值比较方式。<br />枚举值: <br />1：>= <br />2：<= <br />3：> <br />4：< <br />5：== <br />6：!= |**Yes**|
| **RuleSet.N.ThresholdValue** | int | 触发阈值 |**Yes**|
| **RuleSet.N.TriggerCount** | int | 触发次数 |**Yes**|
| **RuleSet.N.SendPeriodType** | string | 触发周期。枚举值：continuous连续 <br />exponent 指数 <br />single 不重复 |**Yes**|
| **RuleSet.N.Level** | string | 告警等级。枚举值：P0,P1,P2,P3 |**Yes**|
| **RuleSet.N.Status** | int | 告警状态。枚举值：0-关闭 1-开启 |**Yes**|
| **RuleSet.N.SendInterval** | int | 沉默周期(告警周期选择为连续时必填) |No|
| **Remark** | string | 备注 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*AlertTemplate*](#AlertTemplate) | 创建告警模板返回对象 |No|

#### 数据模型


#### AlertTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateID** | int | 告警模板ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateAlertStrategyTemplate
&ProjectId=pTKUYkHe
&Name=IFqEXhrk
&ProductKey=tIEzPRln
&RuleSet.N.MetricID=8
&RuleSet.N.ThresholdCompare=1
&RuleSet.N.ThresholdValue=1
&RuleSet.N.TriggerCount=6
&RuleSet.N.SendPeriodType=rQFwFYOx
&RuleSet.N.Level=zPfiXYdy
&RuleSet.N.Status=4
&RuleSet.N.SendInterval=8
&Remark=KvhtYeRp
```

### 响应示例
    
```json
{
  "Action": "CreateAlertStrategyTemplateResponse",
  "Data": {},
  "RetCode": 0
}
```





