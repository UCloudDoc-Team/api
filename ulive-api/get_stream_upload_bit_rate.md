# 获取单个直播推流码率统计 - GetStreamUploadBitRate

## 简介

获取单个直播推流码率统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetStreamUploadBitRate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetStreamUploadBitRate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DomainId** | string | 域名ID，创建域名时生成的ID |**Yes**|
| **StreamName** | string | 流名称 |**Yes**|
| **BeginTime** | int | 查询直播流统计信息的起始时间，格式：时间戳 |**Yes**|
| **EndTime** | int | 查询直播流统计信息的结束时间，不传该参数则返回BeginTime当天的所有统计；实时流信息可以不传此参数。格式：UNIX时间戳。BeginTime与EndTime的区间不能超过24小时。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UploadTraffic** | string | 查询时间段内推流总流量，单位GB |No|
| **MaxBitrate** | string | 从起始时间到结束时间内推流码率峰值 |No|
| **BitrateSet** | array[[*BitrateSet*](#BitrateSet)] | 推流码率数据表，具体参考下面BitrateSet |No|

#### 数据模型


#### BitrateSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点。格式：UNIX时间戳 |No|
| **Value** | string | 推流码率，单位:Kbps |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetStreamUploadBitRate
&DomainId=DAxewKYo
&StreamName=iCLIHKSv
&BeginTime=5
&EndTime=8
```

### 响应示例
    
```json
{
  "Action": "GetStreamUploadBitRateResponse",
  "BitrateSet": [
    {
      "Time": 2,
      "Value": 8.82442
    },
    {
      "Time": 7,
      "Value": 2.35838
    },
    {
      "Time": 4,
      "Value": 3.89456
    },
    {
      "Time": 4,
      "Value": 3.83544
    },
    {
      "Time": 7,
      "Value": 1.59257
    }
  ],
  "MaxBitrate": 8,
  "RetCode": 0,
  "UploadTraffic": 5
}
```





