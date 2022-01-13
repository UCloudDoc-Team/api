# 创建UInfluxdb实例 - CreateUInfluxdbInstance

## 简介

创建UInfluxdb实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUInfluxdbInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUInfluxdbInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 实例名称，长度(6<=size<=63) |**Yes**|
| **Password** | string | 默认账户的密码，需要 base64 编码 |**Yes**|
| **CpuLimit** | int | 核数 单位：个，范围［2C8G, 4C16G, 8C32G, 16C64G, 32C128G］ |**Yes**|
| **MemoryLimit** | int | 内存限制 单位：G 范围 [2C8G, 4C16G, 8C32G, 16C64G, 32C128G］ |**Yes**|
| **ChargeType** | string | 付费类型，后付费阶段固定为：后付费（PostPaid） |**Yes**|
| **Quantity** | int | 购买时长，默认值1 |**Yes**|
| **VPCId** | string | VPC id |**Yes**|
| **SubnetId** | string | 子网 id |**Yes**|
| **AccountName** | string | 默认账户 |**Yes**|
| **DatabaseName** | string | 数据库名称 |**Yes**|
| **Tag** | string | 业务组名称 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UInfluxdbId** | string | 返回的实例id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUInfluxdbInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=PeAZniJG
&Name=lIvvamlz
&QPS=3
&Capacity=1
&CpuLimit=6
&ChargeType=bIGAvNcH
&Quantity=4
&AdminUser=NDLRPETO
&AdminPasswd=FNRTxiXT
&VPCId=YUHsECPp
&SubnetId=vmqmAoYI
&CouponId=JbEIhmcy
&MemoryLimit=6
&Tag=wYlrlGmb
```

### 响应示例
    
```json
{
  "Action": "CreateUInfluxdbInstanceResponse",
  "RetCode": 0
}
```





