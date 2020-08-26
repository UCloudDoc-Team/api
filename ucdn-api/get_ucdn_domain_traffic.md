# 获取加速域名流量使用信息 - GetUcdnDomainTraffic

## 简介

获取加速域名流量使用信息



!> note<br />流量使用数据最长保留3个月的时间。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainTraffic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainTraffic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **AccountType** | string | 指定按项目查询，还是按整个账户查询  取值 top 表示按整个账户查询，取值org表示按项目查询 |No|
| **DomainId.N** | string | 域名ID，创建加速域名时生成，n从自然数0开始。默认全部域名 |No|
| **Areacode** | string | 查询流量区域 cn代表国内 abroad代表海外，默认全部区域 |No|
| **BeginTime** | int | 查询的起始日期，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值 |No|
| **EndTime** | int | 查询的结束日期，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TrafficSet** | array[[*UcdnDomainTrafficSet*](#UcdnDomainTrafficSet)] | 流量实例表，具体结构见 UcdnDomainTrafficSet |No|

#### 数据模型


#### UcdnDomainTrafficSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 流量获取的时间点，格式为Unix Timestamp |No|
| **Value** | float | 查询每日流量总值，单位：GB |No|

## 示例

### 请求示例
    
```
http://api.ucloud.cn/?Action=GetUcdnDomainTraffic
&ProjectId=org-xxxxx
&DomainId.0=ucdn-xxx
&BeginTime=1420992000
&EndTime=1421166064
&Areacode=cn
&AccountType=CjFxZeTe
&AccountType=THIOdFPl
```

### 响应示例
    
```json
{
  " TrafficSet": [
    {
      "Time": " 1399305600",
      "Value": 10.08
    },
    {
      "Time": " 1399392000",
      "Value": 10.08
    },
    {
      "Time": " 1399392000",
      "Value": 10.08
    }
  ],
  "Action": "GetUcdnDomainTrafficResponse",
  "RetCode": 0
}
```





