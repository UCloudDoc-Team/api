# 获取算力平台实例用户价格 - GetCompShareInstanceUserPrice

## 简介

获取算力平台实例用户价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCompShareInstanceUserPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时付费；<br /><br /> Day，按天付费<br /><br /><br /> 如果不传某个枚举值，默认返回月付价格<br /> |No|
| **Cpu** | string | CPU核数。可选范围参照控制台。默认值: 16 |No|
| **Memory** | string | 内存大小。单位：MB。取值为1024的倍数（可选范围参照好控制台）。默认值：32768 |No|
| **Gpu** | string | GPU卡核心数。默认值：1 |No|
| **GpuType** | string | GpuType。枚举值：["4090"] |No|
| **CompShareImageId** | string | 镜像Id |No|
| **Disks.N.Type** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。 |No|
| **Disks.N.Size** | int | 磁盘大小，单位GB。请参考[磁盘类型](api/uhost-api/disk_type)。 |No|
| **Disks.N.IsBoot** | boolean | 是否是系统盘。枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceDetail** | array[[*CompSharePriceDetail*](#CompSharePriceDetail)] | 价格详情列表 |No|
| **OriginalPriceDetail** | array[[*CompSharePriceDetail*](#CompSharePriceDetail)] | 原价详情列表 |No|
| **ListPriceDetail** | array[[*CompSharePriceDetail*](#CompSharePriceDetail)] | 列表价详情列表 |No|

#### 数据模型


#### CompSharePriceDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型 |No|
| **Instance** | float | 实例价格 |No|
| **Disks** | float | 磁盘价格 |No|
| **CompShareImage** | float | 镜像价格/Gpu/小时 |No|
| **OriginalPrice** | float | 原价 |No|
| **ListPrice** | string | 列表价 |No|
| **InstanceDiscountType** | int | 主机折扣类型  1:夜间折扣 2:节日折扣 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCompShareInstanceUserPrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wLCGuXgS
&ChargeType=JzVwgVBT
&Cpu=QHbYUcVG
&Memory=AZvFcsvV
&Gpu=eTiIPXKp
&GpuType=Irxnxwmj
&CompShareImageId=yLJroKZc
&Disks.N.Type=tMUHJHzk
&Disks.N.Size=1
&Disks.N.IsBoot=true
```

### 响应示例
    
```json
{
  "Action": "GetCompShareInstanceUserPriceResponse",
  "ListPriceDetail": [
    {
      "ChargeType": "MjfmoUlt",
      "CompShareImage": 1.56975,
      "Disks": 3.42927,
      "Instance": 2.11734,
      "ListPrice": "bPEBTpmu",
      "OriginalPrice": 6.37637
    }
  ],
  "OriginalPriceDetail": [
    {
      "ChargeType": "ezdrZtEn",
      "CompShareImage": 9.43496,
      "Disks": 9.69113,
      "Instance": 5.32815,
      "ListPrice": "pKlotUNz",
      "OriginalPrice": 9.47224
    }
  ],
  "PriceDetail": [
    {
      "ChargeType": "fIVLkvkR",
      "CompShareImage": 5.69717,
      "Disks": 2.22697,
      "Instance": 1.99356,
      "ListPrice": "rGVmYrDv",
      "OriginalPrice": 1.89391
    }
  ],
  "RetCode": 0
}
```





