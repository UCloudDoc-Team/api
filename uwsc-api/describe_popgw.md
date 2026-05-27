# 查询UWAN虚拟路由器 - DescribePOPGW

## 简介

查询UWAN虚拟路由器






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePOPGW)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePOPGW`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PopGwId** | string | UWAN 实例 ID |**Yes**|
| **Offset** | int | 偏移量 |No|
| **Limit** | int | 限制量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |**Yes**|
| **POPGWInfos** | array[[*POPGWInfo*](#POPGWInfo)] | UWAN 实例信息 |**Yes**|

#### 数据模型


#### POPGWInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域信息 |No|
| **PopGwId** | string | 网关实例 ID |No|
| **Name** | string | 网关名称 |No|
| **Remark** | string | 备注 |No|
| **CreateTime** | int | 创建时间 |No|
| **BWPackageInfo** | [*BWPackageInfo*](#BWPackageInfo) | 带宽包信息 |No|
| **UGNInfo** | [*UGNInfo*](#UGNInfo) | 云联网信息 |No|
| **CPENum** | int | CPE数量 |No|
| **CENum** | int | 客户网关数量 |No|
| **VCPENum** | int | VCPE 数量 |No|
| **VNI** | int | 唯一标识 |No|
| **DueTime** | int | 过期时间 |No|
| **ChargeType** | string | 付费类型 |No|
| **Type** | string | 规格：IPSec、SSL |No|

#### BWPackageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BwId** | string | UWAN 网关带宽 ID |No|
| **Name** | string | 带宽包名称 |No|
| **Remark** | string | 备注 |No|
| **PayMode** | string | 计费方式eg:(固定带宽) |No|
| **ChargeType** | string | 付费方式eg:(Month) |No|
| **PublicIp** | string | 网关外网 IP |No|
| **BandWidth** | float | 最大带宽值 |No|
| **DueTime** | int | 过期时间 |No|

#### UGNInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGNId** | string | 云联网 ID |No|
| **UGNName** | string | 云联网名称 |No|
| **UGNBWInfos** | array[[*UGNBWInfo*](#UGNBWInfo)] | UGN 带宽包信息 |No|

#### UGNBWInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGNBWId** | string | UGN带宽包ID |No|
| **UGNBWName** | string | UGN带宽包名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePOPGW
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XoqSxikV
&PopGwId=oOEZIUIo
&Offset=8
&Limit=5
&Offset=2
&Limit=2
```

### 响应示例
    
```json
{
  "Action": "DescribePOPGWResponse",
  "Message": "wSoEJKBz",
  "POPGWInfos": [
    {
      "BWPackageInfo": {},
      "CEGwNum": 9,
      "CPENum": 8,
      "CreateTime": 7,
      "Name": "NcoAFoiS",
      "PopGwId": "hrKHXycX",
      "Region": "aoHYWbEN",
      "Remark": "rFYAHwrJ",
      "UGNInfo": {},
      "VCPENum": 6
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





