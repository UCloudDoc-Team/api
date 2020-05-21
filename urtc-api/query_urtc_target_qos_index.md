# 查询特定指标 - QueryURtcTargetQosIndex

## 简介

查询特定指标








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcTargetQosIndex`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 待查询的应用id |**Yes**|
| **RoomId** | string | 待查询的房间名 |**Yes**|
| **QueryUser** | string | 待查询的用户名 |**Yes**|
| **StartTime** | int | 秒时间戳 |**Yes**|
| **EndTime** | int | 秒时间戳<br /> |**Yes**|
| **IndexType** | int | 0:common 1:发送方 2.接收方 |**Yes**|
| **IndexName** | int |  IndexType为1：<br />1.上行音频码率 2.上行视频码率  3.上行丢包率 4.采集音量 5.发送延迟 6.帧率<br />IndexType为2 1.下行音频码率 2.下行视频码率  3.下行丢包率 4播放音量 5接收延迟 6.帧率<br />IndexType为0 ：<br />1.app的cpu占用率 2.app的内存数  3.设备的cpu占有率 |**Yes**|
| **SendUser** | string | 当QueryUser为接收方时对应的流发送用户的ID<br />QueryUser为发送方时填成一样 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | array[[*QosItem*](#QosItem)] | 具体返回的值 参加QosItem(time value) |**Yes**|

#### 数据模型


#### QosItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间 |**Yes**|
| **Value** | string | 数值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcTargetQosIndex
&AppId='URtc-h4r1txxy'
&RoomId='2500'
&QueryUser='ssss'
&StartTime=1571196963
&EndTime=1571197963
&IndexType=0
&IndexName=1
&SendUser=HEghJaPl
```

### 响应示例
    
```json
{
  "Action": "QueryURtcTargetQosIndexResponse",
  "Data": [
    {
      "Time": 1571196963,
      "Value": 100
    }
  ],
  "Msg": "Succed",
  "RetCode": 0
}
```





