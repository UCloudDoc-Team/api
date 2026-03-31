# 查询GPU卡余量库存 - DescribeCompShareGpuInventory

## 简介

查询GPU卡余量库存






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCompShareGpuInventory`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GpuInventoryByZone** | object | 返回为嵌套map：，key为池子名称 （Exclusive：独占，Spot ：抢占） value : 库存余量信息map {key 可用区ID，value：GPU卡余量map （key：GPU机型，value：余量GPU卡数量），举例：{"Exclusive":{10027:{"2080":10}}}} |**Yes**|
| **UpdateTime** | int | 缓存更新时间（5min更新一次） |No|
| **SpotUnsupportedGpuTypes** | array[string] | 不支持抢占的GPU机型 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCompShareGpuInventory
&Region=cn-zj
&Zone=cn-zj-01
```

### 响应示例
    
```json
{
  "Action": "DescribeCompShareGpuInventoryResponse",
  "GpuInventoryByZone": {},
  "RetCode": 0,
  "SpotUnsupportedGpuTypes": [
    "NpCbXmdH"
  ],
  "UpdateTime": 2
}
```





