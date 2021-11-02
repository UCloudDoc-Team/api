# 获取直播剩余流量 - GetLiveTrafficRemainV2

## 简介

获取直播剩余流量






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetLiveTrafficRemainV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetLiveTrafficRemainV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TrafficSet** | array[[*TrafficSet*](#TrafficSet)] | 用户不同区域的流量信息表。详见下面TrafficSet |**Yes**|

#### 数据模型


#### TrafficSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Areacode** | string | 购买流量的区域 ，cn代表国内 ，abroad代表海外。 |No|
| **TrafficTotal** | string | areacode区域内总共购买的流量，单位GB |No|
| **TrafficLeft** | string | areacode区域内总共剩余流量，单位GB |No|
| **TrafficUsed** | string | areacode区域内总共使用流量，单位GB |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetLiveTrafficRemainV2
&ProjectId=imIoWDrx
```

### 响应示例
    
```json
{
  "Action": "GetLiveTrafficRemainV2Response",
  "RetCode": 0,
  "TrafficSet": [
    {
      "Areacode": "JHfnRhmN",
      "TrafficLeft": 9.18815,
      "TrafficTotal": 2.78476,
      "TrafficUsed": 9.68646
    }
  ]
}
```





