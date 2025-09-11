# 获取降级任务 - GetCleanServiceResizeContract

## 简介

获取降级任务,不存在降级任务时返回错误









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCleanServiceResizeContract`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id,不允许为空 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceId** | string | 资源ID |**Yes**|
| **BeginTime** | string | 预约开始调整时间 （时间戳） |**Yes**|
| **CleanRegion** | string | 地域 |**Yes**|
| **MaxCleanCapacity** | int | 流量清洗上限防护流量（单位G）5、10、15、20、25 |**Yes**|
| **ChargeType** | string | 计费方式（Month:按月，Year:按年） |**Yes**|
| **Quantity** | int | 防护时长（0代表购置月底，年底），仅降级时有效 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCleanServiceResizeContract
&ResourceId=wMJqpbPN
```

### 响应示例
    
```json
{
  "Action": "GetCleanServiceResizeContractResponse",
  "BeginTime": "hogQIqTB",
  "ChargeType": "Month",
  "CleanRegion": "hCXSbJlP",
  "MaxCleanCapacity": 1,
  "Quantity": 3,
  "ResourceId": "GebkAmBh",
  "RetCode": 0
}
```





