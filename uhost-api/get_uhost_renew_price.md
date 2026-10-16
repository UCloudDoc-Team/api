# 获取主机续费价格 - GetUHostRenewPrice

## 简介

获取主机续费价格

?> 须按照控制台标准机型配置创建主机（例如：无法创建16核1G的非标准机型）。详情请参考控制台。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUHostRenewPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUHostRenewPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID |**Yes**|
| **ChargeType** | string | 计费类型。Year，Month，Dynamic，默认返回全部计费方式对应的价格 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*BasePriceSet*](#BasePriceSet)] | 价格列表 |No|

#### 数据模型


#### BasePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型 |No|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字<br /> |No|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）。<br /> |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUHostRenewPrice
&Region=cn-bj2
&Zone=cn-bj2-04
&ImageId=f43736e1-65a5-4bea-ad2e-8a46e18883c2
&CPU=2
&Memory=4096
&Count=1
&ChargeType=Dynamic
&DiskSpace=10
```

### 响应示例
    
```json
{
  "Action": "GetUHostRenewPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "Dynamic",
      "Price": 0.55
    }
  ],
  "RetCode": 0
}
```





