# 升级加速线路 - UpgradeExportLine

## 简介

升级加速线路






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpgradeExportLine)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeExportLine`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ResourceId** | string | UReach资源ID |**Yes**|
| **PkgType** | string | 目标套餐类型：2M-Entry、5M-Basic、10M-Enterprise |**Yes**|
| **IpType** | string | 原IP类型：International、BGP、Native、Resident |**Yes**|
| **Bandwidth** | int | 带宽大小 |No|
| **ChargeType** | string | 计费模式。枚举值为： Year，按年付费； Month，按月付费； Dynamic，按小时付费（需开启权限）。默认为月付 |No|
| **Quantity** | int | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末。 |No|
| **CouponId** | int | 代金券ID。请登录用户中心查看 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpgradeExportLine
&ProjectId=RocoHieX
&ResourceId=lcmBOsge
&PkgType=rDyrmvyv
&IpType=WSffqIdc
&Bandwidth=2
&ChargeType=Year
&Quantity=5
&CouponId=5
```

### 响应示例
    
```json
{
  "Action": "UpgradeExportLineResponse",
  "Message": "klEQGLAp",
  "RetCode": 0
}
```





