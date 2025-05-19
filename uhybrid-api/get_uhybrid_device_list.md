# 获取混合云设备列表 - GetUhybridDeviceList

## 简介

获取混合云设备列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUhybridDeviceList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUhybridDeviceList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Status.N** | int | 设备状态。枚举值：20-仓库中、40-已上架。 |No|
| **Offset** | int | 起始位置偏移量，默认 0 |No|
| **Limit** | int | 返回数据长度，默认 20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*UhybridDevice*](#UhybridDevice)] | 设备资源 |No|
| **TotalCount** | int | 设备资源总数 |No|

#### 数据模型


#### UhybridDevice

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UUID** | string | 设备UUID |No|
| **SN** | string | 设备SN |No|
| **Alias** | string | 设备别名 |No|
| **RackNumber** | string | 机柜编号 |No|
| **RackId** | string | 机柜 UUID |No|
| **Status** | int | 设备状态(20-仓库中、40-已上架) |No|
| **Type** | string | 设备类型（server - 服务器、switch - 网络设备） |No|
| **CompanyId** | int | 公司ID |No|
| **CompanyName** | string | 公司名称 |No|
| **OrganizationId** | int | 项目ID |No|
| **PhysicalName** | string | 物理机房 |No|
| **PhysicalNameCN** | string | 物理机房中文 |No|
| **LogicalName** | string | 逻辑机房 |No|
| **ShortId** | string | 短资源ID |No|
| **LongId** | string | 长资源ID |No|
| **ZoneId** | int | 可用区ID |No|
| **ZoneCN** | string | 可用区中文 |No|
| **RegionId** | int | 区域ID |No|
| **Position** | int | U位 |No|
| **Height** | int | 高度 |No|
| **Remarks** | string | 备注 |No|
| **UServerZoneId** | int | 专区ID |No|
| **Owner** | int | 归属：0-默认,1-UCloud,2-客户 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUhybridDeviceList
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ZkBwRKaR
&Status=3
&Offset=6
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "GetUhybridDeviceListResponse",
  "Data": [
    {
      "RackId": "oXkummsu",
      "RackNumber": "CONhMaiS",
      "SN": "nqbKbhVr",
      "Status": 2,
      "Type": "essSOKdz",
      "UUID": "RFCNTDfc"
    }
  ],
  "RetCode": 0,
  "TotalCount": 8
}
```





