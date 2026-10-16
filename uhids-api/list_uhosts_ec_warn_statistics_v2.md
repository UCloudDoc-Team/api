# 获取当前账号与项目下的各类主机安全告警统计值 - ListUHostsecWarnStatisticsV2

## 简介

获取当前账号与项目下的各类主机安全告警统计值，但不统计暴力破解失败数据，SshBruteFailed为0









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUHostsecWarnStatisticsV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **WarnStatistics** | [*WarnStatistics*](#WarnStatistics) | 主机安全各告警统计值 |No|

#### 数据模型


#### WarnStatistics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BaseCheck** | int | 安全基线检查告警统计值 |**Yes**|
| **AbnormalLogin** | int | 异常登录告警统计值 |**Yes**|
| **SshBruteSucceeded** | int | 暴力破解成功告警统计值 |**Yes**|
| **Trojan** | int | 木马告警统计值 |**Yes**|
| **VulCheck** | int | 漏洞检查告警统计值 |**Yes**|
| **SshBruteFailed** | int | 暴力破解失败统计值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUHostsecWarnStatisticsV2
&ProjectId=IdkiNkgL
```

### 响应示例
    
```json
{
  "Action": "ListUHostsecWarnStatisticsV2Response",
  "RetCode": 0,
  "WarnStatistics": {
    "AbnormalLogin": 15,
    "BaseCheck": 5,
    "SshBruteFailed": 0,
    "SshBruteSucceeded": 4,
    "Trojan": 3,
    "VulCheck": 73
  }
}
```





