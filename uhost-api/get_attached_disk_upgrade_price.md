# 获取挂载磁盘的升级价格 - GetAttachedDiskUpgradePrice

## 简介

获取挂载磁盘的升级价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAttachedDiskUpgradePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAttachedDiskUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DiskSpace** | int | 磁盘大小，单位GB。取值范围需大于当前磁盘大小，最大值请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **DiskId** | string | 磁盘ID。参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)返回值中的DiskSet。 |**Yes**|
| **UHostId** | string | UHost实例ID。 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)。 |**Yes**|
| **BackupMode** | string | 磁盘备份方案。枚举值：<br /><br /> > NONE，无备份 <br /><br /> > DATAARK，数据方舟 <br /><br />> SNAPSHOT(SNAPSHOT模式目前仅在上海C支持)，快照 <br /><br /> 当前磁盘支持的备份模式参考 [磁盘类型](api/uhost-api/disk_type)。默认值为当前的备份模式。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 升级差价。精度为小数点后2位。 |No|
| **OriginalPrice** | float | 用户折后价。精度为小数点后2位。 |No|
| **ListPrice** | float | 原价。精度为小数点后2位。 |No|
| **PriceDetail** | [*DiskUpgradePriceDetail*](#DiskUpgradePriceDetail) | 升级价格详情，精度为小数点后2位。 |No|
| **OriginalPriceDetail** | [*DiskUpgradePriceDetail*](#DiskUpgradePriceDetail) | 用户折后价详情，精度为小数点后2位。 |No|
| **ListPriceDetail** | [*DiskUpgradePriceDetail*](#DiskUpgradePriceDetail) | 原价详情，精度为小数点后2位。 |No|

#### 数据模型


#### DiskUpgradePriceDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UDisk** | float | 磁盘的价格 |No|
| **Snapshot** | float | 快照的价格 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAttachedDiskUpgradePrice
&Region=mxTjdPUG
&Zone=GxCoXGWk
&ProjectId=abcdNzFG
&DiskSpace=8
&DiskId=zPpZIRGk
&UHostId=wRVYAONq
&BackupMode=NONE
```

### 响应示例
    
```json
{
  "Action": "GetAttachedDiskUpgradePriceResponse",
  "ListPrice": 3.45338,
  "ListPriceDetail": {},
  "ListlPrice": 5.32126,
  "OriginalPrice": 1.85482,
  "OriginalPriceDetail": {},
  "Price": 3.26,
  "PriceDetail": {},
  "RetCode": 0
}
```





