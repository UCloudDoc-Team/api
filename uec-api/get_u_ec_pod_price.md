# 获得容器组价格 - GetUEcPodPrice

## 简介

获得容器组价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEcPodPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IdcId** | string | 机房id |**Yes**|
| **CpuCore** | float | 容器组总Cpu核心数 |No|
| **MemSize** | int | 容器组总内存大小（单位M） |No|
| **ChargeType** | int | 支付类型（2按月，3按年，默认2） |No|
| **ChargeQuantity** | int | 月数或年数（默认值：1，当支付类型为按月时，默认值为0） |No|
| **ProductType** | string | 产品类型（normal：标准型，hf：高性能型，默认：normal） |No|
| **ElasticIp** | string | 是否绑定外网IP（yes：是，no：否，默认：no） |No|
| **Bandwidth** | int | 绑定的带宽，默认0，当绑定外网IP时默认1（单位M） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HolderPrice** | float | 容器组价格 |**Yes**|
| **IpPrice** | float | IP和带宽价格 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEcPodPrice
&IdcId=EDpXPoZm
&CpuCore=4.28575
&MemSize=9
&ChargeType=5
&ChargeQuantity=4
&ProductType=ETeOGKGM
&ElasticIp=TwoSdSDi
&Bandwidth=2
```

### 响应示例
    
```json
{
  "Action": "GetUEcPodPriceResponse",
  "HolderPrice": 1.67843,
  "IpPrice": 6.26955,
  "RetCode": 0
}
```





