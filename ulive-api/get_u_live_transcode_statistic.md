# 获取直播转码计费统计信息 - GetULiveTranscodeStatistic

## 简介

获取直播转码计费统计信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveTranscodeStatistic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveTranscodeStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **StartTime** | int | 起始时间。时间戳 |**Yes**|
| **EndTime** | int | 结束时间。时间戳 |**Yes**|
| **TimeGranularity** | int | 粒度。5分钟 TimeGranularity=5;1小时 TimeGranularity=60;1天 TimeGranularity=1440 |**Yes**|
| **Domain.N** | string | 域名，如果不传该参数则获取用户帐号下所有直播域名配置信息,n为自然数多个域名 一次从0增加 |No|
| **Area** | string | 区域，cn：国内；abroad：国外；all：全部。默认值为cn |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*GetTranscodeChargeInfoDataChart*](#GetTranscodeChargeInfoDataChart)] |  |**Yes**|

#### 数据模型


#### GetTranscodeChargeInfoDataChart

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间戳 |**Yes**|
| **H264480P** | int | h.264 480p分辨率时长 |**Yes**|
| **H264720P** | int | h.264 720p分辨率时长 |**Yes**|
| **H2641080P** | int | h.264 1080p分辨率时长 |**Yes**|
| **H2642K** | int | h.264 2K分辨率时长 |**Yes**|
| **H2644K** | int | h.264 4K分辨率时长 |**Yes**|
| **H265480P** | int | h.265 480p分辨率时长 |**Yes**|
| **H265720P** | int | h.265 720p分辨率时长 |**Yes**|
| **H2651080P** | int | h.265 1080p分辨率时长 |**Yes**|
| **H2652K** | int | h.265 2K分辨率时长 |**Yes**|
| **H2654K** | int | h.265 4K分辨率时长 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveTranscodeStatistic
&ProjectId=sZgKeZJi
&StartTime=9
&EndTime=3
&TimeGranularity=9
&SubType=5
&Domain.n=eqTUIwCR
```

### 响应示例
    
```json
{
  "Action": "GetULiveTranscodeStatisticResponse",
  "Data": [
    {
      "H2641080P": 1,
      "H2642K": 3,
      "H264480P": 5,
      "H2644K": 5,
      "H264720P": 4,
      "H2651080P": 6,
      "H2652K": 9,
      "H265480P": 3,
      "H2654K": 8,
      "H265720P": 3,
      "Time": 3
    }
  ],
  "RetCode": 0
}
```





