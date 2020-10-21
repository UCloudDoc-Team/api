# 【待下线】获取流量信息 - GetUcdnTraffic

## 简介

获取流量信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnTraffic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnTraffic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TrafficSet** | array[[*TrafficSet*](#TrafficSet)] | 用户不同区域的流量信息, 具体结构参见TrafficSet部分 |No|

#### 数据模型


#### TrafficSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Areacode** | string | 购买流量的区域, cn: 国内; abroad: 国外 |No|
| **TrafficTotal** | float | Areacode区域内总购买流量, 单位GB |No|
| **TrafficLeft** | float | Areacode区域内总剩余流量, 单位GB |No|
| **TrafficUsed** | float | Areacode区域内总使用流量, 单位GB |No|

## 示例

### 请求示例
    
```
http://api.ucloud.cn/?Action=GetUcdnTraffic
&ProjectId=xxxxx
```

### 响应示例
    
```json
{
  "Action": "GetUcdnTrafficResponse",
  "RetCode": 0,
  "TrafficSet": [
    {
      "Areacode": "cn",
      "TrafficLeft": 100.1,
      "TrafficTotal": 120,
      "TrafficUsed": 19.9
    },
    {
      "Areacode": "abroad",
      "TrafficLeft": 100.1,
      "TrafficTotal": 120,
      "TrafficUsed": 19.9
    }
  ]
}
```





