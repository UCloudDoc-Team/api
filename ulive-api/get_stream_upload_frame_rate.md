# 获取单个直播推流视频帧率统计 - GetStreamUploadFrameRate

## 简介

获取单个直播推流视频帧率统计（现仅支持视频帧率统计，不支持音频帧率统计）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetStreamUploadFrameRate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetStreamUploadFrameRate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DomainId** | string | 域名ID，创建域名时生成的ID |**Yes**|
| **StreamName** | string | 流名称；等同于其他接口的streamid参数 |**Yes**|
| **BeginTime** | int | 查询直播流统计信息的起始时间，格式：UNIX时间戳 |**Yes**|
| **EndTime** | int | 查询直播流统计信息的结束时间，不传该参数则返回BeginTime当天的所有统计；实时流信息可以不传此参数。格式：UNIX时间戳。BeginTime与EndTime区间不能超过24小时。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FrameRateSet** | array[[*FrameRateSet*](#FrameRateSet)] | 推流帧率数据表，具体参考下面FrameRateSet |No|

#### 数据模型


#### FrameRateSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点。格式：UNIX时间戳 |**Yes**|
| **Value** | string | 推流帧率，单位:f/s（帧/秒） |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetStreamUploadFrameRate
&DomainId=jppBCpyD
&StreamName=BSVnqtbg
&BeginTime=4
&EndTime=4
```

### 响应示例
    
```json
{
  "Action": "GetStreamUploadFrameRateResponse",
  "FrameRateSet": [
    {
      "Time": 2,
      "Value": 1.59637
    },
    {
      "Time": 2,
      "Value": 9.26737
    },
    {
      "Time": 2,
      "Value": 7.37918
    },
    {
      "Time": 2,
      "Value": 5.48518
    },
    {
      "Time": 9,
      "Value": 7.17982
    },
    {
      "Time": 2,
      "Value": 1.37371
    },
    {
      "Time": 3,
      "Value": 6.76721
    },
    {
      "Time": 3,
      "Value": 5.61533
    },
    {
      "Time": 7,
      "Value": 9.59437
    },
    {
      "Time": 9,
      "Value": 9.85641
    }
  ],
  "RetCode": 0
}
```





