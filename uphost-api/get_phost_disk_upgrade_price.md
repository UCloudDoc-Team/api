# 获取物理云裸金属挂载云盘的升级价格 - GetPHostDiskUpgradePrice

## 简介

获取物理云裸金属挂载磁盘的升级价格



!> 必须是裸金属机型此接口有效


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetPHostDiskUpgradePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetPHostDiskUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PHostId** | string | UPHost实例ID。 |**Yes**|
| **DiskSpace** | int | 磁盘大小，单位GB，必须是10GB的整数倍。系统盘20-500GB，数据盘单块盘20-32000GB。 |**Yes**|
| **UDiskId** | string | 磁盘 ID。获取扩容价格必填（只能扩不能减）；重装时候不需要填（根据所选盘大小决定） |No|
| **ReinstallTag** | boolean | 是否重装价格获取。复用此接口。扩容只能增加云盘大小。重装不限制。枚举值：true/false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 升级差价。精度为小数点后2位。 |**Yes**|
| **OriginalPrice** | float | 升价差价原价。精度为小数点后2位。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetPHostDiskUpgradePrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=btTvhpal
&PHostId=APyurAbq
&DiskSpace=5
&UDiskId=GcwAWPhw
&ReinstallTag=false
```

### 响应示例
    
```json
{
  "Action": "GetPHostDiskUpgradePriceResponse",
  "OriginalPrice": 1.85835,
  "Price": 8.55895,
  "RetCode": 0
}
```





