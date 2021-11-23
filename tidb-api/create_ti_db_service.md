# 创建服务 - CreateTiDBService

## 简介

创建TiDB服务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateTiDBService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateTiDBService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目 ID |**Yes**|
| **Name** | string | 服务名称， 长度不超过64 |**Yes**|
| **Password** | string | 服务root账号的密码， 长度不超过32 |**Yes**|
| **VPCId** | string | VPC ID |**Yes**|
| **SubnetId** | string | 子网 ID |**Yes**|
| **TikvMemoryHardTh** | string | 实例类型:   0: 旗舰版，30: 体验版，60: 轻量版  |No|
| **Ip** | string | ipv4 |No|
| **Port** | string | 端口 |No|
| **DTType** | string | 容灾类型：10:同可用区，20:跨可用区，默认是同可用区 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*ServiceID*](#ServiceID) | Service Data |No|
| **ServiceId** | string | 服务ID |No|

#### 数据模型


#### ServiceID

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 服务ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateTiDBService
&Region=cn-zj
&Name=pIEIVhHC
&Password=pwGmuGAr
&AccessVPCId=fHryqwgY
&SubnetId=zqaEcBmm
&ProjectId=IsdeuBDd
&TikvMemoryHardTh=cxfMqVOa
&Ip=IchjnUte
&Port=6
&DTType=ATRPviKe
```

### 响应示例
    
```json
{
  "Action": "CreateTiDBServiceResponse",
  "Data": {},
  "Message": "DqzmVrUE",
  "RetCode": 0,
  "ServiceId": "xVJLjxzc"
}
```





