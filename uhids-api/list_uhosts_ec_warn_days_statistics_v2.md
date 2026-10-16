# 获取按天列出各类告警统计值 - ListUHostsecWarnDaysStatisticsV2

## 简介

获取按天列出各类告警统计值，但不统计暴力破解失败数据，SshBruteFailed为0









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUHostsecWarnDaysStatisticsV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **StartTime** | string | 统计开始时间(y-m-d hh:mm:ss)。不填写默认从一周前开始统计 |No|
| **EndTime** | string | 统计结束时间(y-m-d hh:mm:ss)。不填写默认为当前时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Statistics** | array[[*Statistics*](#Statistics)] | 按天的统计对象数组 |**Yes**|

#### 数据模型


#### Statistics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Date** | string | 进行告警统计的时间 |**Yes**|
| **BaseCheck** | int | 安全基线检查告警统计值 |**Yes**|
| **AbnormalLogin** | int | 异常登录告警统计值 |**Yes**|
| **SshBruteSucceeded** | int | 暴力破解成功告警统计值 |**Yes**|
| **SshBruteFailed** | int | 暴力破解失败统计值 |**Yes**|
| **Trojan** | int | 木马告警统计值 |**Yes**|
| **VulCheck** | int | 漏洞检查告警统计值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUHostsecWarnDaysStatisticsV2
&ProjectId=FyFZMrbc
&StartTime=NTwdDMoh
&EndTime=NwAZPGPe
```

### 响应示例
    
```json
{
  "Action": "ListUHostsecWarnDaysStatisticsV2Response",
  "RetCode": 0,
  "Statistics": [
    {
      "AbnormalLogin": 7,
      "BaseCheck": 4,
      "Date": "dbNWmcTX",
      "SshBruteFailed": 3,
      "SshBruteSucceeded": 1,
      "Trojan": 3,
      "VulCheck": 2
    }
  ]
}
```





