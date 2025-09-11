# 获取清洗流量历史统计 - GetCleanServiceStatistics

## 简介

获取清洗流量历史统计









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCleanServiceStatistics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id,不允许为空 |**Yes**|
| **BeginTime** | string | 查询开始时间 |**Yes**|
| **EndTime** | string | 查询结束时间 |**Yes**|
| **DefenceIP** | string | 当DefenceIP为空时，接口返回资源所处区域内被攻击流量最大的5个IP;<br />当DefenceIP为某一IP时，接口返回资源所处区域内该IP的清洗前后流量数据; |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DefenceIPList** | array[string] | 当DefenceIP为空时，仅返回TOP 5 流量的IP数组列表 |**Yes**|
| **CleanStatistics** | string | 当DefenceIP表示单个IP时，仅返回此项。代表指定时间内该IP的PPS和BPS等信息 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCleanServiceStatistics
&ResourceId=usecure_UCLEAN-2cy3wd
&top_organization_id=200000103
&organization_id=200000217
&account_id=200000103
&BeginTime=1523089529
&EndTime=1593089529
&DefenceIP=120.132.20.20

```

### 响应示例
    
```json
{
  "Action": "GetCleanServiceStatisticsResponse",
  "DefenceIPList": [
    "106.75.145.36",
    "106.75.175.222",
    "106.75.49.5",
    "120.132.20.20"
  ],
  "RetCode": 0
}
```





