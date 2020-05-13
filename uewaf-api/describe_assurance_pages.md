# 获取防篡改页面列表 - DescribeAssurancePages

## 简介

获取防篡改页面列表





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeAssurancePages)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAssurancePages`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Domain** | string | 要获取的域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Res** | [*AssurancePages*](#AssurancePages) | 防篡改信息，参考AssurancePages |No|

#### 数据模型


#### AssurancePages

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **State** | string | 防篡改全局状态 |**Yes**|
| **TotalCount** | int | 防篡改配置总数 |**Yes**|
| **Limit** | int | 防篡改规则配额 |**Yes**|
| **Items** | array[[*AssuracePagesDetail*](#AssuracePagesDetail)] | 防篡改规则列表，参考AssuracePagesDetail |**Yes**|

#### AssuracePagesDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | 反篡改规则ID |**Yes**|
| **URL** | string | 防篡改页面url |**Yes**|
| **State** | string | 防护状态 |**Yes**|
| **Remark** | string | 备注信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAssurancePages
&ProjectId=org-xxx
&Domain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeAssurancePagesResponse",
  "Res": {
    "Items": [
      {
        "Id": 368,
        "Remark": "q",
        "State": "on",
        "Url": "http://www.test.com/inedx.html"
      }
    ],
    "Limit": 19,
    "State": "off",
    "TotalCount": 1
  },
  "RetCode": 0
}
```





