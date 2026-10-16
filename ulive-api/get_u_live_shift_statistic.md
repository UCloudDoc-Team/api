# 直播时移统计信息(计费) - GetULiveShiftStatistic

## 简介

GetULiveShiftStatistic 直播时移计费信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveShiftStatistic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveShiftStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Domain.N** | string | 域名，如果不传该参数则获取用户帐号下所有直播域名 |**Yes**|
| **StartTime** | int | 查询起始时间，格式：时间戳。 |**Yes**|
| **EndTime** | int | 查询结束时间，格式：时间戳。 |**Yes**|
| **TimeGranularity** | int | 查询粒度，包含：1，5，60。1 1分钟；5 5分钟;60 1小时 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ULiveShiftStatisticDataChat*](#ULiveShiftStatisticDataChat)] |  |**Yes**|

#### 数据模型


#### ULiveShiftStatisticDataChat

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点，格式：时间戳 |**Yes**|
| **Size** | int | 时移带宽数据，单位：Mbps |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveShiftStatistic
&ProjectId=vCWHKdEY
&Domain.n=VVSjVxxa
&StartTime=5
&EndTime=5
&TimeGranularity=2
```

### 响应示例
    
```json
{
  "Action": "GetULiveShiftStatisticResponse",
  "Data": [
    {
      "Size": 1,
      "Time": 6
    }
  ],
  "RetCode": 0
}
```





