# 获取直播加速带宽 ---【需要下线】 - GetUcdnLiveAccessBandwidth

## 简介

获取直播加速带宽 -- 【需要下线】

?> 待下线




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnLiveAccessBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnLiveAccessBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId.N** | string | 域名ID，创建加速域名时生成。 |**Yes**|
| **Type** | int | 流量查询粒度，0:5分钟；1:1小时；2:1天 |**Yes**|
| **Protocol** | string | 播放协议，rtmp/hls，不传则获取带宽总和 |No|
| **BeginTime** | int | 查询流量的起始时间，格式：时间戳 |No|
| **EndTime** | int | 查询流量的结束时间，格式：时间戳 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BandwidthSet** | array[[*UcdnLiveAccessBandwidthSet*](#UcdnLiveAccessBandwidthSet)] | 带宽流量实例表。具体参考下面 UcdnLiveAccessBandwidthSet |No|
| **Traffic** | float | 从起始时间到结束时间内所使用的总流量，单位GB |No|

#### 数据模型


#### UcdnLiveAccessBandwidthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

## 示例

### 请求示例
    
```
http://api.spark.ucloud.cn/?Action=GetUcdnLiveAccessBandwidth
&DomainId.0=domain-0331qd
&Type=0
```

### 响应示例
    
```json
{
  "Action": "GetUcdnLiveAccessBandwidthResponse",
  "BandwidthSet": [
    {
      "Time": 1399305600,
      "Value": 1.05
    },
    {
      "Time": 1399305900,
      "Value": 1.05
    }
  ],
  "RetCode": 0,
  "Traffic": 0
}
```





