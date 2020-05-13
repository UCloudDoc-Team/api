# 获取主机价格 - GetUHostInstancePrice

## 简介

根据UHost实例配置，获取UHost实例的价格。





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUHostInstancePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUHostInstancePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **CPU** | int | CPU核数。可选参数：1-64。可选范围参照控制台。默认值: 4 |**Yes**|
| **Memory** | int | 内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参照好控制台）。默认值：8192 |**Yes**|
| **Count** | int | 购买台数，范围[1,5] |**Yes**|
| **Disks.N.IsBoot** | string | 是否是系统盘。枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Disks.N.Size** | int | 磁盘大小，单位GB。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.Type** | string | 磁盘类型。请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **Disks.N.BackupType** | string | 磁盘备份方案。枚举值：<br /><br /> > NONE，无备份 <br /><br /> > DATAARK，数据方舟 <br /><br /> 当前磁盘支持的备份模式参考 [磁盘类型](api/uhost-api/disk_type) |No|
| **ImageId** | string | 镜像Id，可通过 [DescribeImage](api/uhost-api/describe_image) 获取镜像ID， 如果镜像ID不传，系统盘大小必传 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段。 |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Dynamic，按小时付费 <br /><br /> 默认为月付。 |No|
| **NetCapability** | string | 网络增强。枚举值：Normal，不开启; Super，开启网络增强1.0。 默认值为Normal。 |No|
| **UHostType** | string | 【待废弃】云主机机型（V1版本概念）。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **MachineType** | string | 云主机机型（V2版本概念）。枚举值["N", "C", "G", "O"]。参考[云主机机型说明](api/uhost-api/uhost_type)。 |No|
| **GpuType** | string | GPU类型，枚举值["K80", "P40", "V100"] |No|
| **Quantity** | int | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末。 |No|
| **CpuPlatform** | string | 取值"Intel" "Amd"，默认值“Intel” |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UHostPriceSet*](#UHostPriceSet)] | 价格列表 UHostPriceSet |No|

#### 数据模型


#### UHostPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型。Year，Month，Dynamic |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字 |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）。 |**Yes**|
| **ListPrice** | float | 产品列表价。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUHostInstancePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&ImageId=xxx
&MachineType=N
&CPU=2
&Memory=4096
&Count=1
&ChargeType=Dynamic
&Disks.0.Size=40
&Disks.0.IsBoot=True
&Disks.0.Type=CLOUD_SSD
&CpuPlatform=pmuJsysU
```

### 响应示例
    
```json
{
  "Action": "GetUHostInstancePriceResponse",
  "PriceSet": [
    {
      "ChargeType": "Dynamic",
      "Price": 0.42
    }
  ],
  "RetCode": 0
}
```





