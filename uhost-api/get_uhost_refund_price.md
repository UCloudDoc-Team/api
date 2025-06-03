# 获取主机删除扣除费用 - GetUHostRefundPrice

## 简介

获取主机删除扣除费用。包括主机、磁盘、快照服务、EIP等资源的费用






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUHostRefundPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUHostRefundPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostIds.N** | string | 【数组】UHost实例ID。参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RefundPriceSet** | array[[*UHostRefundPriceSet*](#UHostRefundPriceSet)] | 主机删除扣除费用详情 |**Yes**|

#### 数据模型


#### UHostRefundPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UHostId** | string | UHost实例ID |**Yes**|
| **Code** | int | 实例操作结果的错误码。0为成功 |**Yes**|
| **Message** | string | 当 Code 非 0 时提供详细的描述信息 |No|
| **RefundPrice** | float | 实例的删除退费金额 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUHostRefundPrice
&Region=cn-zj
&ProjectId=QsUFgUbN
&UHostIds.N=GJgMMTbb
```

### 响应示例
    
```json
{
  "Action": "GetUHostRefundPriceResponse",
  "RefundPriceSet": [
    {
      "Code": 2,
      "Message": "lrftRADV",
      "RefundPrice": 6.87196,
      "UHostId": "UrRlsdui"
    }
  ],
  "RetCode": 0
}
```





