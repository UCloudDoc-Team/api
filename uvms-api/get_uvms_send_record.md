# 获取语音发送记录 - GetUVMSSendRecord

## 简介

获取语音发送记录

?> 拉取时间为半年，跨度为7天







## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUVMSSendRecord`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Page** | int | 页码，默认0 |No|
| **NumPerPage** | int | 每页数量，默认10 |No|
| **OrderBy** | string | call_start_time(拨打时间)/receive_time（回执时间） |No|
| **OrderType** | string | asc<br />desc |No|
| **StartTime** | float | 开始时间-拨打时间，时间戳（秒），默认最近7天 |No|
| **EndTime** | float | 结束时间-拨打时间，时间戳（秒），默认当前 |No|
| **FuzzySearch** | string | 模糊搜索，支持 主叫号码和被叫号码 |No|
| **TaskNo** | string | 任务编号 |No|
| **BrevityCode** | string | 国际码，国内CN |No|
| **ExcludeBrevityCode** | string | 排除国际码 |No|
| **Purpose** | int | 目标1验证码2通知3营销 |No|
| **PhoneNumber** | string | 被叫号码，精确查询 |No|
| **TemplateId** | string | 目标ID |No|
| **CalledCityCode** | string | 被叫城市编码 |No|
| **CalledOperatorCode** | string | 被叫运营商 cmcc中国移动，cucc中国联通,ctcc中国电信 |No|
| **CallingCityCode** | string | 主叫城市编码 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Total** | int | 总数 |No|
| **Data** | array[[*SendRecordItem*](#SendRecordItem)] | 发送数据 |No|

#### 数据模型


#### SendRecordItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskNo** | string | 任务编号 |No|
| **Phone** | string | 被叫号码 |No|
| **ShowNumber** | string | 主叫号码，如果是随机，可能为空 |No|
| **PreCost** | int | 预扣量 |No|
| **Purpose** | int | 目标1验证码2通知3营销 |No|
| **BrevityCode** | string | 国际码 |No|
| **CountryCode** | string | 国家码 |No|
| **TemplateId** | string | 模板ID |No|
| **CallStartTime** | float | 呼叫开始时间(毫秒时间戳) |No|
| **CallEndTime** | float | 呼叫结束时间(毫秒时间戳) |No|
| **Duration** | int | 呼叫持续时间 |No|
| **ChannelId** | string | 通道ID |No|
| **ReceiptResult** | int | 回执结果1成功2失败3未知 |No|
| **ReceiptDesc** | string | 回执描述 |No|
| **ReceiveTime** | float | 回执时间 |No|
| **CallingCityCode** | string | 主叫所属城市码 |No|
| **CalledCityCode** | string | 被叫所属城市码 |No|
| **CalledOperatorCode** | string | 被叫供应商码 cmcc中国移动，cucc中国联通,ctcc中国电信 |No|
| **SubmitTime** | float | 客户提交时间 |No|
| **GroupType** | int | 1随机号码组2专属号码组 |No|
| **BillSecond** | int | 计费时长（秒） |No|
| **BillPeriod** | int | 计费周期（秒） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUVMSSendRecord
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=gfKXAbhT
&Page=8
&NumPerPage=1
&OrderBy=ndPxrXsy
&OrderType=yZRZzhnr
&StartTime=9
&EndTime=2
&FuzzySearch=ebHKurrj
&TaskNo=HopxsvvB
&BrevityCode=DUuUFBQC
&ExcludeBrevityCode=oaGlvjYQ
&Purpose=8
&PhoneNumber=CfzhkvrM
&TemplateId=FbdvnEwm
&CalledCityCode=TbeNwioS
&CalledIspCode=wiDtWDVN
&CallingCityCode=BFNVCWTI
```

### 响应示例
    
```json
{
  "Action": "GetUVMSSendRecordResponse",
  "Count": 4,
  "Data": [
    {
      "BrevityCode": "FIatdAGY",
      "CallEndTime": 2,
      "CallStartTime": 1,
      "CalledCityCode": "nFijTrZh",
      "CalledIspCode": "jDHXqErI",
      "CallingCityCode": "yOcCMPrX",
      "ChannelId": "TyEwkYbv",
      "CountryCode": "Ttnpesra",
      "Duration": 6,
      "Phone": "pYEkTLXQ",
      "PreCost": 5,
      "Purpose": 1,
      "ReceiptDesc": "qGnCeoRb",
      "ReceiptResult": 2,
      "ReceiveTime": 4,
      "ShowNumber": "rgsGxfOo",
      "SubmitTime": 8,
      "TaskNo": "LaKWtHtK",
      "TemplateId": "BRfIRbKp"
    }
  ],
  "RetCode": 0
}
```





