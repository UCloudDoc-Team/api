# 购买高防服务 - BuyHighProtectGameService

## 简介

购买高防服务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BuyHighProtectGameService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BuyHighProtectGameService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ChargeType** | string | 计费方式 ,取值范围 {"Month",  "Year", "Dynamic", "Day"};其中华东双线周付使用Day,其他支持的周付使用Dynamic; |**Yes**|
| **Quantity** | int | 计费时长 |**Yes**|
| **LineType** | string | 'default': 'DUPLET',  取值范围 {"DUPLET", "BGP"} |**Yes**|
| **AreaLine** | string | 线路区域, 可取范围{"SouthChina",   "EastChina"} |**Yes**|
| **SrcBandwidth** | int | 带宽 |**Yes**|
| **EngineRoom.N** | string | 购买的套餐所在机房，取值范围{"Hangzhou2",  "Hangzhou", "Xiamen"} |**Yes**|
| **DefenceType** | string | 防御类型，默认为TypeFixed; 取值范围{"TypeFixed",  "TypeDynamic"} |No|
| **HighProtectGameServiceName** | string | 高防服务名称 |No|
| **Vendor** | int | 供应商编号 |No|
| **DefenceDDosBaseFlowArr.N** | string | DDoS基础防护值（当购买套餐为多种线路的时候，顺序为，电信，联通，移动...，当为单线的时候只传DefenceDDosBaseFlowArr.0） |No|
| **DefenceDDosMaxFlowArr.N** | string | DDoS最大防护值（当购买套餐为多种线路的时候，顺序为，电信，联通，移动...；当为单线的时候只传DefenceDDosMaxFlowArr.0） |No|
| **ForwardType** | string | 转发类型，默认为：Proxy；Proxy：代理、Passthrough：直连  |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceInfo** | [*ResourceInfo*](#ResourceInfo) | 返回的用户资源信息 |**Yes**|

#### 数据模型


#### ResourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BuyHighProtectGameService
&ChargeType="Month"
&DefenceType="TypeFixed"
&DefenceDDosBaseFlow=10
&DefenceDDosMaxFlow=20
&Quantity=1
&CouponId="93d238b6"
&HighProtectGameServiceName="bgp_test"
&LineType="BGP"
&ResourceId="ab3607ef-3fa8-4a6e-9872-33175f5612ba"
&ChangePayMode="BuyGame"
&DefenceDDosMaxFlowArr="20,20"
&DefenceDDosBaseFlowArr="10,10"
&EngineRoom="Hangzhou"
&AreaLine="EastChina"
&SrcBandwidth=10
&ChargeIPQuota=1
&EngineRoom=ajrRhaNd
&Vendor=8
&EngineRoom.1=VADeOllO
&DefenceDDosMaxFlowArr.1=XDLNLRdu
&DefenceDDosBaseFlowArr.1=kbyavTaR
&AccessMode=DMYpuJPf
&AccessMode=ycttAjiB
&ProjectId=fKyQBaha
&AccessMode=aMLmIgCR
&ForwardType=RvpwuQuG
```

### 响应示例
    
```json
{
  "Action": "BuyHighProtectGameServiceResponse",
  "ResourceInfo": "{ResourceId: xxx, Region: xxx}",
  "RetCode": 0
}
```





