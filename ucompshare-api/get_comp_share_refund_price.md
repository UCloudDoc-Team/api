# 获取算力平台实例删除扣除费用 - GetCompShareRefundPrice

## 简介

获取算力平台实例删除扣除费用。包括主机、磁盘等资源的费用






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCompShareRefundPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist)<br /> |**Yes**|
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
| **ErrMessage** | string | 当 Code 非 0 时提供详细的描述信息 |No|
| **RefundPrice** | float | 实例的删除退费金额 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCompShareRefundPrice
&Region=cn-zj
&ProjectId=xooEoJtD
&UHostIds.N=aKtQyego
&Zone=cn-zj-01
```

### 响应示例
    
```json
{
  "Action": "GetCompShareRefundPriceResponse",
  "RefundPriceSet": [
    {
      "Code": 2,
      "Message": "lWsknlPy",
      "RefundPrice": 4.69928,
      "UHostId": "vowzragJ"
    }
  ],
  "RetCode": 0
}
```





