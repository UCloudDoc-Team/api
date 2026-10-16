# 获取攻击中Ip的信息 - GetUSAIpInfosUnderAtk

## 简介

获取攻击中Ip的信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSAIpInfosUnderAtk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IpInfos** | array[[*IpInfoUnderAtk*](#IpInfoUnderAtk)] | IpInfoUnderAtk数组 |**Yes**|
| **TotalCount** | int | 返回的IpInfoUnderAtk的条目数 |No|

#### 数据模型


#### IpInfoUnderAtk

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | Ip地址 |No|
| **Type** | int | 0=Eip, 1=托管IP, 2=AnycastEIP |No|
| **RegionId** | int | Regin Id |No|
| **Status** | int | 0-正常,1-清洗中,2-封堵中 |No|
| **StartTime** | int | 事件开始时间 |No|
| **EndTime** | int | 事件即将结束的时间 |No|
| **BlockThreshold** | int | 该IP的封堵阈值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSAIpInfosUnderAtk
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=PqUAQfAf
&BeginTime=CNvNMHFc
&EndTime=CrQzyTqH
```

### 响应示例
    
```json
{
  "Action": "GetUSAIpInfosUnderAtkResponse",
  "IpInfos": [
    {
      "BlockThreshold": 1,
      "Ip": "103.72.146.106",
      "RegionId": 3001,
      "StartTime": 1568190138,
      "Status": 2,
      "StopTime": 1568276538,
      "Type": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





