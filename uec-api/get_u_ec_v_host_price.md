# 获取虚拟机价格 - GetUEcVHostPrice

## 简介

获取虚拟机价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEcVHostPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IdcId** | string | 机房Id |**Yes**|
| **NodeCount** | int | 节点数量，默认1 |No|
| **CpuCore** | int | CPU核数 |No|
| **MemSize** | int | 内存大小，单位GB |No|
| **SysDiskSize** | int | 系统盘大小，单位GB |No|
| **DiskSize** | int | 数据盘大小，单位GB |No|
| **NetLimit** | int | 网络带宽限速，单位Mbs |No|
| **ChargeType** | int | 付费方式，1按时，2按月，3按年，默认2 |No|
| **ChargeQuantity** | int | 月数或者年数，0计费到月底， 默认0 |No|
| **ProductType** | string | 产品类型：normal（经济型），hf（标准型），g(Gpu型),默认normal |No|
| **IpCount** | int | 外网IP的数量，默认1 |No|
| **Gpu** | int | Gpu卡核心数。仅Gpu机型支持此字段 |No|
| **GpuType** | string | Gpu类型，枚举值["T4"],ProductType为g时必填 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodePrice** | float | 节点价格 |No|
| **IpPrice** | float | Ip和带宽价格 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEcVHostPrice
&IdcId=LIWzMASE
&NodeCount=6
&CpuCore=2
&MemSize=5
&SysDiskSize=5
&DiskSize=9
&NetLimit=5
&ChargeType=7
&ChargeQuantity=6
&ProductType=iZqfxAyg
&IpCount=2
&Gpu=2
&GpuType=AmSGDjhO
```

### 响应示例
    
```json
{
  "Action": "GetUEcVHostPriceResponse",
  "IpPrice": 2.33868,
  "NodePrice": 8.59262,
  "RetCode": 0
}
```





