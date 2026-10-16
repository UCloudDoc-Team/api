# 直播录制统计信息 - GetULiveRecordStatistic

## 简介

直播录制统计信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveRecordStatistic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveRecordStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **StartTime** | int | 查询起始时间，时间戳 |**Yes**|
| **EndTime** | int | 查询结束时间，时间戳 |**Yes**|
| **TimeGranularity** | int | 粒度。1分钟，TimeGranularity=1;5分钟 TimeGranularity=5 |**Yes**|
| **Domain.N** | string | 域名，如果不传该参数则获取用户帐号下所有直播域名 |No|
| **Area** | string | 区域，cn：国内；abroad：国外；all：全部。默认值cn |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ULiveRecordStatisticDataChat*](#ULiveRecordStatisticDataChat)] |  |**Yes**|

#### 数据模型


#### ULiveRecordStatisticDataChat

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点，格式：时间戳 |**Yes**|
| **Duration** | int | 录制文件时长 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveRecordStatistic
&ProjectId=DwfquYGy
&StartTime=1
&EndTime=4
&TimeGranularity=7
&Domain.n=GXYyPXvS
&Region=BGhppfhM
```

### 响应示例
    
```json
{
  "Action": "GetULiveRecordStatisticResponse",
  "Data": [
    {
      "Duration": 9,
      "Time": 8
    }
  ],
  "RetCode": 0
}
```





