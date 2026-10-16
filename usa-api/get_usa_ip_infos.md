# 获取ip的状态信息 - GetUSAIpInfos

## 简介

获取ip的状态信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSAIpInfos`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | string | 开始时间, 默认不传时赋值为　当前时间-6天 |No|
| **EndTime** | string | 结束时间,默认不传时　　　　当前时间 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为100 |No|
| **Ip** | string | 允许根据指定Ip来查询攻击记录, 如果没有则表示是全部查．<br />目前仅仅支持传入１个IP地址 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IpInfos** | array[[*IpInfo*](#IpInfo)] | ip信息 |**Yes**|
| **TotalCount** | int | 总个数 |**Yes**|

#### 数据模型


#### IpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | Ip地址 |No|
| **Type** | int | 0=Eip, 1=托管IP, 2=AnycastEIP |No|
| **RegionId** | int | Regin Id |No|
| **Status** | int | 0-正常,1-清洗中,2-封堵中 |No|
| **BlockThreshold** | int | 该IP的封堵阈值 |No|
| **AtkCount** | int | 历史累计次数 |No|
| **AtkPeakBps** | float | 历史攻击峰值 |No|
| **AtkLastTime** | int | 最后一次攻击的时间点 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSAIpInfos
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=qAbMtOtF
&Offset=2
&Limit=8
&Ip=FEFltWyS
&Ip=OYIkGUSb
&BeginTime=hIaUOafW
&EndTime=geLyGEPd
```

### 响应示例
    
```json
{
  "Action": "GetUSAIpInfosResponse",
  "IpInfos": [
    {
      "AtkCount": 5,
      "AtkLastTime": 1568170956,
      "AtkPeakBps": 0,
      "BlockThreshold": 1,
      "Ip": "107.150.103.166",
      "RegionId": 6001,
      "Status": 0,
      "Type": 0
    },
    {
      "AtkCount": 3,
      "AtkLastTime": 1568170207,
      "AtkPeakBps": 0,
      "BlockThreshold": 1,
      "Ip": "107.150.125.214",
      "RegionId": 3001,
      "Status": 0,
      "Type": 0
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





