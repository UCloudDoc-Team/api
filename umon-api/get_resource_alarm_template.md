# 获取资源绑定的告警模板 - GetResourceAlarmTemplate

## 简介

获取资源绑定的告警模板





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetResourceAlarmTemplate)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetResourceAlarmTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ResourceType** | string | 资源类型（与DescribeResourceMetric中一致） |**Yes**|
| **ResourceId.N** | string | 资源id列表 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*ResourceTemplateBound*](#ResourceTemplateBound)] | 请见ResourceTemplateBound |**Yes**|

#### 数据模型


#### ResourceTemplateBound

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **HasAlarmTemlate** | string | 是否绑定了告警模板，Yes：是；No：否。若为No，不展示AlarmTemplateId、AlarmTemplateName、Remark |**Yes**|
| **ResourceId** | string | 资源id |**Yes**|
| **AlarmTemplateId** | int | 告警模板id |No|
| **AlarmTemplateName** | string | 告警模板名称 |No|
| **IsDefault** | string | 是否默认模板，Yes：是；No：否 |No|
| **Remark** | string | 模板备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetResourceAlarmTemplate
&Region=cn-bj2
&ProjectId=org-kk3qlr
&ResourceType=uhost
&ResourceId.0=uhost-xxx
&IsGlobal=5
```

### 响应示例
    
```json
{
  "Action": "GetResourceAlarmTemplateResponse",
  "DataSet": [
    {
      "AlarmTemplateId": 4,
      "AlarmTemplateName": "默认云主机告警模板",
      "HasAlarmTemplate": "Yes",
      "IsDefault": "Yes",
      "Remark": "默认推荐模板",
      "ResourceId": "uhost-mwzal2",
      "uuid": "9943290f-da50-4edf-a80f-xxxxx"
    }
  ],
  "RetCode": 0
}
```





