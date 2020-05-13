# 获取告警模板列表 - GetAlarmTemplateList

## 简介

获取告警模板列表





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAlarmTemplateList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAlarmTemplateList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list) |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数量 |**Yes**|
| **DataSet** | array[[*AlarmTemplate*](#AlarmTemplate)] | 告警模板列表 |**Yes**|

#### 数据模型


#### AlarmTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AlarmTemplateId** | int | 告警模板id |**Yes**|
| **AlarmTemplateName** | string | 告警模板名称 |**Yes**|
| **ResourceType** | string | 资源类型 |**Yes**|
| **BoundResourceCount** | int | 绑定的资源数量 |**Yes**|
| **IsGlobal** | int | 是否是全局机房模版，0不是，1是 |**Yes**|
| **IsDefault** | string | 是否为默认模板 |No|
| **Remark** | string | 备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAlarmTemplateList
&Region=DGdSoave
&ProjectId=EzXfGltN
&Limit=UjSBCcay
&Offset=tMJXiqNF
&ResourceType=YsEmOUYC
```

### 响应示例
    
```json
{
  "Action": "GetAlarmTemplateListResponse",
  "DataSet": [
    {
      "AlarmTemplateId": 1,
      "AlarmTemplateName": "THwnZpbV",
      "BoundResourceCount": 8,
      "IsDefault": "Yes",
      "Remark": "pJavCcAz",
      "ResourceType": "UaCrdVJM"
    },
    {
      "AlarmTemplateId": 9,
      "AlarmTemplateName": "nDCuUndt",
      "BoundResourceCount": 2,
      "IsDefault": "Yes",
      "Remark": "zhMGrkaK",
      "ResourceType": "KPJLDerL"
    },
    {
      "AlarmTemplateId": 4,
      "AlarmTemplateName": "ZRHjuLLX",
      "BoundResourceCount": 4,
      "IsDefault": "Yes",
      "Remark": "wpGNxXwu",
      "ResourceType": "tzJzMuuz"
    },
    {
      "AlarmTemplateId": 4,
      "AlarmTemplateName": "zbiIKPnV",
      "BoundResourceCount": 6,
      "IsDefault": "Yes",
      "Remark": "sIHLdiXA",
      "ResourceType": "kduqaLUb"
    },
    {
      "AlarmTemplateId": 6,
      "AlarmTemplateName": "DBMweHYH",
      "BoundResourceCount": 8,
      "IsDefault": "Yes",
      "Remark": "YJqRXyiC",
      "ResourceType": "zfqEzXCT"
    },
    {
      "AlarmTemplateId": 6,
      "AlarmTemplateName": "zDtcJJXm",
      "BoundResourceCount": 1,
      "IsDefault": "Yes",
      "Remark": "DsZQaLGz",
      "ResourceType": "rKvQzdmV"
    },
    {
      "AlarmTemplateId": 3,
      "AlarmTemplateName": "PHdOzEwQ",
      "BoundResourceCount": 9,
      "IsDefault": "Yes",
      "Remark": "bXJvUkBz",
      "ResourceType": "JXXAlxSz"
    },
    {
      "AlarmTemplateId": 6,
      "AlarmTemplateName": "AnQVcuMA",
      "BoundResourceCount": 9,
      "IsDefault": "Yes",
      "Remark": "oNaALals",
      "ResourceType": "OFddPTcu"
    }
  ],
  "RetCode": 0,
  "TotalCount": 4
}
```





