# 获取历史推流列表 - GetULiveHistoryStreamList

## 简介

获取历史推流记录列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveHistoryStreamList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveHistoryStreamList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询开始时间，UNIX时间戳格式 |**Yes**|
| **EndTime** | int | 查询结束时间，UNIX时间戳格式 |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **StreamName** | string | 流名称；等同于其他接口的streamid参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HistorStreamList** | array[[*HistorStreamList*](#HistorStreamList)] | 历史流列表 |**Yes**|

#### 数据模型


#### HistorStreamList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |No|
| **StreamName** | string | 流名 |No|
| **Application** | string | 接入点 |No|
| **TimeSlot** | array[string] | 时间段集合，示例：["1644325052-1644325092","1644324052-1644325062"]表示这路流在查询时间段内出现的时间段集合 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveHistoryStreamList
&ProjectId=KiaEWjZJ
&BeginTime=5
&EndTime=2
&Domain=HLGLZKxg
&StreamName=NJLdiEva
```

### 响应示例
    
```json
{
  "Action": "GetULiveHistoryStreamListResponse",
  "HistorStreamList": [
    {
      "Application": "tJOxxexM",
      "Domain": "PmMHCeQO",
      "StreamName": "TLMOrDue",
      "TimeSlot": [
        "zRYfwySv"
      ]
    }
  ],
  "RetCode": 0
}
```





