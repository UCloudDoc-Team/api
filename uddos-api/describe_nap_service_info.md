# 获取高防服务信息 - DescribeNapServiceInfo

## 简介

获取高防服务信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNapServiceInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNapServiceInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | 资源ID |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为10 |No|
| **NapType** | int | 高防类型；0：全部、1：内地高防、2：海外高防 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ServiceInfo** | array[[*ServiceInfo*](#ServiceInfo)] | 高防服务信息 |No|
| **TotalCount** | int | 总数 |No|

#### 数据模型


#### ServiceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |No|
| **ResourceId** | string | 资源ID |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpiredTime** | int | 过期时间 |No|
| **DefenceDDosMaxFlowArr** | array[int] | 套餐最大防护组 |No|
| **DefenceDDosBaseFlowArr** | array[int] | 套餐基础防护组 |No|
| **AutoRenew** | string | 是否开启自动续费 |No|
| **RegionId** | int | region id |No|
| **DefenceType** | string | 防护类型 |No|
| **ChargeType** | string | 付费类型 |No|
| **DefenceStatus** | string | 防护状态，Started：正常、Stopped：关闭、Expired：过期 |No|
| **Name** | string | 套餐名称 |No|
| **LineType** | string | 线路类型 |No|
| **EngineRoom** | array[string] | 防护机房名称 |No|
| **AreaLine** | string | 防护机房所在区域 |No|
| **SrcBandwidth** | int | 业务带宽 |No|
| **GameId** | int | 套餐ID |No|
| **Vendor** | int | 供应商ID |No|
| **AccessMode** | string | 接入模式，Domain：网站接入、IP：非网站接入 |No|
| **ForwardType** | string | 转发类型，Proxy：代理、Passthrough：直连 |No|
| **NapType** | int | 高防类型，1：内地高防、2：海外高防 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNapServiceInfo
&ResourceId=XaOcJuwP
&Offset=2
&Limit=5
&NapType=9
&ProjectId=RuuWyHRU
```

### 响应示例
    
```json
{
  "Action": "DescribeNapServiceInfoResponse",
  "RetCode": 0,
  "ServiceInfo": "hQBZmVBD",
  "TotalCount": 6
}
```





