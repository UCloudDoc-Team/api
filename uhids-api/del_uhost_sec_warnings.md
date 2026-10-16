# 删除告警 - DelUHostSecWarnings

## 简介

删除告警



!> 删除安全事件的告警信息，从界面显示中频闭掉该告警记录的显示，如果该安全事件依然存在，被复检或者下次巡检发现依然会触发告警，重新在界面显示.





## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DelUHostSecWarnings`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Data** | string | 要删除告警的列表json格式：{"Data":[{"WarnType":"WebShellAlarm","ID":"59e870483ef9f419617b7744"},{"WarnType":"checkCockhorse","ID":"59f67a26812c307b65d72e99"}]}）WarnType类型：WebShellAlarm，checkCockhorse，BaseCheck，webRisk,VulCheck2，AbnormalLogin，SshBruteSucceeded |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DelUHostSecWarnings
&ProjectId=fSDNYbYe
&Data=FVOgPWEt
```

### 响应示例
    
```json
{
  "Action": "DelUHostSecWarningsResponse",
  "RetCode": 0
}
```





