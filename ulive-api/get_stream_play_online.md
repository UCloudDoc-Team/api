# 获取单个主播播放在线人数统计 - GetStreamPlayOnline

## 简介

获取单个主播播放在线人数统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetStreamPlayOnline)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetStreamPlayOnline`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DomainId** | string | 域名ID，创建域名时生成的ID |**Yes**|
| **StreamName** | string | 流名称 |**Yes**|
| **BeginTime** | int | 查询直播流统计信息的起始时间，格式：时间戳 |**Yes**|
| **EndTime** | int | 查询直播流统计信息的结束时间，不传该参数则返回BeginTime当天的所有统计；实时流信息可以不传此参数。格式：UNIX时间戳。BeginTime与EndTime区间不能超过24小时。 |No|
| **PlayDomain** | string | 播放域名，不传此参数则获取该DomainId下所有播放域名的数据 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **OnlineSet** | array[[*OnlineSet*](#OnlineSet)] | 播放在线数据表，具体参考下面OnlineSet |No|

#### 数据模型


#### OnlineSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点。格式：UNIX时间戳 |**Yes**|
| **Value** | float | 在线人数，单位:人 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetStreamPlayOnline
&DomainId=DfknHGan
&StreamName=wVLywBaO
&BeginTime=3
&EndTime=5
```

### 响应示例
    
```json
{
  "Action": "GetStreamPlayOnlineResponse",
  "FrameRateSet": [
    {
      "Time": 6,
      "Value": 2.76412
    },
    {
      "Time": 6,
      "Value": 3.55444
    },
    {
      "Time": 4,
      "Value": 9.68424
    },
    {
      "Time": 4,
      "Value": 8.57226
    },
    {
      "Time": 2,
      "Value": 3.49365
    }
  ],
  "RetCode": 0
}
```





