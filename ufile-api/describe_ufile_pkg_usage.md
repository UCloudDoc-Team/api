# 查询资源包使用明细 - DescribeUFilePkgUsage

## 简介

查询资源包使用明细




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFilePkgUsage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFilePkgUsage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | 资源包ID |**Yes**|
| **StartDate** | string | 开始时间，如 2023-09-01 |**Yes**|
| **EndDate** | string | 结束时间，如 2023-09-01 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Usage** | array[[*PkgUsage*](#PkgUsage)] | 按天返回的使用明细 |No|

#### 数据模型


#### PkgUsage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Date** | string | 日期 |No|
| **Cost** | string | 使用量，单位为B |No|

## 示例

### 请求示例

```
https://api.ucloud.cn/?Action=DescribeUFilePkgUsage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=YORqQeIF
&ResourceId=SUjjyZiG
&StartDate=2023-09-01
&EndDate=2023-09-30
```

### 响应示例

```json
{
  "Action": "DescribeUFilePkgUsageResponse",
  "Usage": [
    {
      "Date": "2023-09-01",
      "Cost": "1024"
    }
  ],
  "RetCode": 0
}
```




