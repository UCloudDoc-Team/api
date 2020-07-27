# 创建并挂载云硬盘 - CreateAttachUDisk

## 简介

创建并挂载UDisk磁盘

?> "17092": "该磁盘版本过低，无法开启数据方舟"




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateAttachUDisk)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateAttachUDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 购买UDisk大小,单位:GB,普通数据盘：范围[1\~8000]；SSD数据盘：范围[1\~8000]；RSSD数据盘：范围[1\~32000]。 |**Yes**|
| **Name** | string | 实例名称 |**Yes**|
| **UHostId** | string | 当创建云盘类型为RSSDDataDisk时，根据传入的UHostId，创建与虚机在同一PodId下的云盘 |**Yes**|
| **ChargeType** | string | Year , Month, Dynamic, Postpay, Trial 。 Size小于等于2000时，默认为Dynamic；Size大于2000时，默认为Month。 |No|
| **Quantity** | int | 购买时长 默认: 1 |No|
| **UDataArkMode** | string | 【即将废弃，开启快照服务时，免费开启数据方舟】是否开启数据方舟。Yes：开启，No：不开启，默认值：No |No|
| **SnapshotService** | string | 是否开启快照服务。Yes：开启，No：不开启，默认值：No |No|
| **Tag** | string | 业务组 默认：Default |No|
| **DiskType** | string | UDisk 类型: DataDisk（普通数据盘），SSDDataDisk（SSD数据盘），RSSDDataDisk（RSSD数据盘），默认值（DataDisk） |No|
| **UKmsMode** | string | 是否加密。Yes：加密，No：不加密，默认值（No） |No|
| **CmkId** | string | 加密需要的cmk id，UKmsMode为Yes时，必填 |No|
| **MultiAttach** | string | 是否允许多点挂载（Yes: 允许多点挂载， No: 不允许多点挂载， 不填默认Yes ） |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDiskId** | string | 挂载的UDisk实例ID |No|
| **UHostId** | string | 挂载的UHost实例ID |No|
| **DeviceName** | string | 挂载设备名称 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateAttachUDisk
&Region=fePADFDK
&Zone=nZVkTEeG
&ProjectId=lBYhRYwK
&Size=2
&Name=dRnLmEsF
&ChargeType=Year
&Quantity=3
&UDataArkMode=Yes
&Tag=ANUJBMxl
&DiskType=rdyjaTAh
&UKmsMode=UWdWyhmS
&CmkId=XYYNHuCm
&UHostIdForAttachment=hgLBzxKT
&CouponId=XHavHbdB
&MultiAttach=yyMqSgep
&MultiAttach=ejvSWdAP
&SnapshotService=VlgfpSlc
```

### 响应示例
    
```json
{
  "Action": "CreateAttachUDiskResponse",
  "DeviceName": "lGfgoKdq",
  "RetCode": 0,
  "UDiskId": [
    "lVjpdPEC"
  ],
  "UHostId": "gZjemlLv"
}
```





