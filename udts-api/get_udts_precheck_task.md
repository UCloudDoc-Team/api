# 获取 precheck 结果 - GetUDTSPrecheckTask

## 简介

获取 precheck 结果






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDTSPrecheckTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TaskId** | string | 任务ID |**Yes**|
| **Type** | string | 任务类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*CheckResult*](#CheckResult) | 预检查结果 |**Yes**|

#### 数据模型


#### CheckResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **State** | string | 预检查任务状态 |No|
| **PrecheckResultItem** | array[[*CheckResultItem*](#CheckResultItem)] | 预检查项目 |No|

#### CheckResultItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **State** | string | 状态 |**Yes**|
| **Type** | string | 检查类型 |**Yes**|
| **ErrMessage** | string | 错误信息 |**Yes**|
| **Instruction** | string | 解决方案 |**Yes**|
| **IsTarget** | boolean | 是否对目标库的检查结果 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDTSPrecheckTask
&ProjectId=QAYgheFF
&TaskId=xNcUaeHI
&Type=MdOHoRGC
```

### 响应示例
    
```json
{
  "Action": "GetUDTSPrecheckTaskResponse",
  "Data": {},
  "Message": "UdAxekmr",
  "RetCode": 0
}
```





