# 获取监控概况数据 - GetMetricOverview

## 简介

获取资源当前各项监控指标数据

?> <br />note<br />资源类型及监控指标，参见 GetMetric文档<br /><br />




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetMetricOverview)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetMetricOverview`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填为默认项目。子账户必须填写项目ID |No|
| **ResourceType** | string | 资源类型 |**Yes**|
| **MetricName.N** | string | 监控指标名称，若省略则返回所有监控指标数据 |No|
| **Limit** | int | 数据分页值，默认为20 |No|
| **Offset** | int | 数据偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*ResourceItemSet*](#ResourceItemSet)] | JSON格式监控数据列表 |No|
| **RefreshTime** | int | 系统更新时间，格式为Unix Timestamp |No|
| **ResourceType** | string | 资源类型 |No|
| **TotalCount** | int | 返回总数量 |No|

#### 数据模型


#### ResourceItemSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |No|
| **Name** | string | 资源名称 |No|
| **MetricName** | string | 对应监控项的监控数据 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?action=GetMetricOverview
&Region=cn-bj2
&Zone=cn-bj2-04
&ResourceType=uhost
```

### 响应示例
    
```json
{
  "Action": "GetMetricOverviewResponse",
  "DataSet": [
    {
      "BlockProcessCount": 0,
      "CPUUtilization": 0,
      "DataSpaceUsage": 0,
      "DiskReadOps": 0,
      "DiskWriteOps": 0,
      "IORead": 0,
      "IOWrite": 4641,
      "MemUsage": 0,
      "NICIn": 3002,
      "NICOut": 3944,
      "Name": "testtest",
      "NetPacketIn": 2,
      "NetPacketOut": 2,
      "Remark": "",
      "ResourceId": "uhost-xxx",
      "RootSpaceUsage": 0,
      "RunnableProcessCount": 0,
      "Uuid": "0e796e5a-e004-42a2-92be-77277bde9144"
    }
  ],
  "RefreshTime": 1431507033,
  "ResourceType": "uhost",
  "RetCode": 0,
  "TotalCount": 1
}
```





