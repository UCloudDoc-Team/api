# 获取带宽用量 - DescribeBandwidthUsage

## 简介

获取带宽用量信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBandwidthUsage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBandwidthUsage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Limit** | int | 返回数据分页值, 取值范围为 [0,10000000] 之间的整数, 默认为20 |No|
| **OffSet** | int | 返回数据偏移量, 默认为0 |No|
| **EIPIds.N** | string | 弹性IP的资源Id. 如果为空, 则返回当前 Region中符合条件的所有EIP的带宽用量, n为自然数 |No|
| **BeginTime** | int | 统计开始时间 |No|
| **EndTime** | int | 统计结束时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | EIPSet中的元素个数 |No|
| **EIPSet** | array[[*UnetBandwidthUsageEIPSet*](#UnetBandwidthUsageEIPSet)] | 单个弹性IP的带宽用量详细信息, 详见 UnetBandwidthUsageEIPSet, 如没有弹性IP资源则没有该返回值。 |No|

#### 数据模型


#### UnetBandwidthUsageEIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CurBandwidth** | float | 最近5分钟带宽用量, 单位Mbps |No|
| **EIPId** | string | 弹性IP资源ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeBandwidthUsage
&Region=cn-bj2
&EIP.0=eip-XXX
&BeginTime=7
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "DescribeBandwidthUsageResponse",
  "EIPSet": [
    {
      "CurBandwidth": 0.0000629425048828125,
      "EIPId": "eip-XXXX"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





