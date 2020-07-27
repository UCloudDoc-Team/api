# 导出工作流定义 - GetSFWorkflowTemplate

## 简介

导出工作流定义






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSFWorkflowTemplate)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSFWorkflowTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **WorkflowId** | string | 被导出工作流的Id |**Yes**|
| **WorkflowVersion** | int | 被导出工作流的版本号。取值范围：WorkflowVersion >= 1；默认会获取发布版本对应的workflow；超过最大版本会返回错误 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **WorkflowId** | string | 导出工作流的Id |**Yes**|
| **Version** | int | 导出工作流的版本号 |**Yes**|
| **Workflow** | [*WorkflowTemplate*](#WorkflowTemplate) | 工作流定义，详细信息见工作流对象定义 |**Yes**|

#### 数据模型


#### WorkflowTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Input** | array[[*Param*](#Param)] | 工作流的输入，详细信息见Param |No|
| **Output** | array[[*Param*](#Param)] | 工作流的输出，详细信息见Param |No|
| **Activites** | array[[*ActivityTemplate*](#ActivityTemplate)] | 工作流的Activities，详细信息见工作流的Activity定义 |No|

#### Param

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 参数名称 |No|
| **Type** | string | 参数类型 |No|
| **Value** | string | 参数值 |No|

#### ActivityTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | Activity的名字<br /> |No|
| **Type** | string | Activity的类型<br /> |No|
| **RetryTimes** | string | 	<br />Activity的重试次数 |No|
| **Timeout** | string | Activity的超时时间 |No|
| **Next** | string | 下一个Activity的名字 |No|
| **Input** | object | Activity的输入 |No|
| **Output** | array[string] | Activity的输出，详见Param |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSFWorkflowTemplate 
&Region=cn-bj2
&ProjectId=pAZhEbkU
&WorkflowId=fdhoGtKK
&WorkflowVersion=1
```

### 响应示例
    
```json
{
  "Action": "GetSFWorkflowTemplateResponse",
  "Message": "success",
  "RetCode": 0,
  "Version": 1,
  "Workflow": {
    "Activities": [
      {
        "Input": null,
        "Name": "start",
        "Next": "step934",
        "Output": null,
        "RetryTimes": 0,
        "Timeout": 600000,
        "Type": "StartActivity"
      },
      {
        "Input": null,
        "Name": "end",
        "Next": "",
        "Output": null,
        "RetryTimes": 0,
        "Timeout": 600000,
        "Type": "EndActivity"
      },
      {
        "Input": {
          "body": {
            "UserID": "${workflow.input.UserID}",
            "UserName": "${workflow.input.UserName}"
          },
          "header": {
            "ContentType": "application/json"
          },
          "isAsync": false,
          "method": "GET",
          "query": {
            "Action": "VerifyUser"
          },
          "retrytimes": 0,
          "timeout": 0,
          "url": "http://52.165.220.33/api/json/est/now"
        },
        "Name": "step934",
        "Next": "end",
        "Output": null,
        "RetryTimes": 0,
        "Timeout": 600000,
        "Type": "HttpActivity"
      }
    ],
    "Input": [
      {
        "Constrain": null,
        "Name": "UserID",
        "Type": "INT64",
        "Value": ""
      },
      {
        "Constrain": null,
        "Name": "UserName",
        "Type": "STRING",
        "Value": ""
      }
    ],
    "Output": []
  },
  "WorkflowId": "craig-qq4nqG.import_case_low"
}
```





