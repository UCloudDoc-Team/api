# 获取直连高防IP信息 - DescribePassthroughNapIP

## 简介

获取直连高防IP信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePassthroughNapIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePassthroughNapIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 高防资源ID |**Yes**|
| **NapIp** | string | 高防IP |No|
| **Limit** | int | 限制(传EIPs.0时暂时无效) |No|
| **Offset** | int | 位偏移(传EIPs.0时暂时无效) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | IP总个数 |**Yes**|
| **AvailableIPQuota** | int | 合法IP配额 |**Yes**|
| **IPInfo** | array[[*IPInfo*](#IPInfo)] | EIP信息 |**Yes**|

#### 数据模型


#### IPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIPAddr** | array[[*EIPAddrSet*](#EIPAddrSet)] | 高防IP信息 |No|
| **Tag** | string | 业务组 |No|
| **Status** | string | 状态 |No|
| **CreateTime** | int | 创建时间 |No|
| **EIPRegion** | string | EIP Region |No|
| **EIPId** | string | EIP资源ID |No|
| **Resource** | [*Resouce*](#Resouce) | 资源信息 |No|

#### EIPAddrSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | 弹性IP地址 |No|
| **EIPType** | string | IP类型：gaofang |No|
| **OperatorName** | string | 运营商信息, 枚举值为:  BGP: BGP; International: 国际. |No|

#### Resouce

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 地区 |No|
| **ResourceType** | string | 资源类型 |No|
| **ResourceName** | string | 资源名 |No|
| **ResourceId** | string | 资源ID |No|
| **EIPId** | string | EIP资源ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePassthroughNapIP
&Region=cn-zj
&ProjectId=hFyMGfYi
&TopOrganizationId=2
&OrganizationId=9
&ResourceId=6
&EIPIDs.0=ziAvaGtK
&IPs.0=XlfPuzaq
&Limit=8
&Offset=6
```

### 响应示例
    
```json
{
  "Action": "DescribePassthroughNapIPResponse",
  "EIPSet": {},
  "Message": "vBNdSPkG",
  "RetCode": 0,
  "TotalBandwidth": "aWkSTeDJ",
  "TotalCount": "TouhQsCc",
  "UnbindCount": "ZumJlHGK"
}
```





