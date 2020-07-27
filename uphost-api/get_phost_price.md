# 获取物理机价格 - GetPHostPrice

## 简介

获取物理机价格列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetPHostPrice)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetPHostPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Count** | int | 购买数量，范围[1-5] |**Yes**|
| **ChargeType** | string | 计费模式，枚举值为： Year/Month/Trial/Dynamic |**Yes**|
| **Quantity** | int | 购买时长，1-10个月或1-10年 |**Yes**|
| **Cluster** | string | 网络环境，可选千兆：1G ；万兆：10G；25G网络：25G。 |No|
| **Type** | string | 默认为：DB(数据库型)，可以通过接口 [DescribePHostMachineType](api/uphost-api/describe_phost_machine_type.html)获取 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*PHostPriceSet*](#PHostPriceSet)] | 价格列表 见 PHostPriceSet |No|

#### 数据模型


#### PHostPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year/Month/Trial/Dynamic |No|
| **Price** | float | 价格, 单位:元, 保留小数点后两位有效数字 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetPHostPrice
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&Count=1
&ChargeType=Month
&Quantity=1
&Type=DB
&Cluster=FRkegmUL
&Cluster=DYEIfcVe
```

### 响应示例
    
```json
{
  "Action": "GetPHostPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "Month",
      "Price": 3600
    }
  ],
  "RetCode": 0
}
```





