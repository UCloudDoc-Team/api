# 查询可购买的资源包列表 - DescribeUFileAvailablePkg

## 简介

查询可购买的资源包列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFileAvailablePkg)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFileAvailablePkg`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PkgList** | array[[*AvailablePkg*](#AvailablePkg)] | 可购买的资源包规格 |**Yes**|

#### 数据模型


#### AvailablePkg

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | int | 资源类型ID |No|
| **Name** | string | 资源类型名称 |No|
| **Specs** | array[[*AvailablePkgSpecs*](#AvailablePkgSpecs)] | 支持购买的数量规格 |No|
| **CommonDurations** | array[[*AvailablePkgDurations*](#AvailablePkgDurations)] | 公共支持购买的时长，当一个Spec配了独立的Durations时，就按独立配置Durations生效；否者按CommonDurations生效 |No|

#### AvailablePkgSpecs

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Durations** | array[[*AvailablePkgDurations*](#AvailablePkgDurations)] | 仅针对当前规格生效的durations |**Yes**|
| **Amount** | int | 购买数量 |No|
| **Unit** | string | 数量的单位，如：GB，TB |No|

#### AvailablePkgDurations

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Discount** | float | 折扣 |**Yes**|
| **Duration** | int | 购买时长 |No|
| **Unit** | string | 时长单位，如: Month、Year |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFileAvailablePkg
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=yTrzqOsP
```

### 响应示例
    
```json
{
  "Action": "DescribeUFileAvailablePkgResponse",
  "PkgList": [
    {
      "CommonDurations": [
        {
          "Duration": 1,
          "Unit": "Month"
        },
        {
          "Duration": 2,
          "Unit": "Month"
        },
        {
          "Duration": 3,
          "Unit": "Month"
        },
        {
          "Duration": 4,
          "Unit": "Month"
        },
        {
          "Duration": 6,
          "Unit": "Month"
        },
        {
          "Duration": 12,
          "Unit": "Month"
        },
        {
          "Duration": 24,
          "Unit": "Month"
        }
      ],
      "Name": "StandardStorage",
      "Specs": [
        {
          "Amount": 40,
          "Durations": [
            {
              "Duration": 6,
              "Unit": "Month"
            },
            {
              "Duration": 12,
              "Unit": "Month"
            },
            {
              "Duration": 24,
              "Unit": "Month"
            }
          ],
          "Unit": "GB"
        },
        {
          "Amount": 100,
          "Unit": "GB"
        },
        {
          "Amount": 500,
          "Unit": "GB"
        },
        {
          "Amount": 1,
          "Unit": "TB"
        }
      ],
      "Type": 0
    }
  ],
  "RetCode": 0
}
```





