# 获取视频短信发送状态回执 - GetISMSSendReceipt

## 简介

获取视频短信发送记录的状态回执









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetISMSSendReceipt`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TaskIdSet.N** | string | 发送记录TaskId集合。调用SendUSMSVideoMessage时返回的TaskId的集合。以TaskIdSet.0、TaskIdSet.1...TaskIdSet.N的形式传入。每次请求最多支持100个 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 本次请求uuid |**Yes**|
| **Data** | array[[*ReceiptPerTask*](#ReceiptPerTask)] | 本次请求结果 |No|

#### 数据模型


#### ReceiptPerTask

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 发送短信时返回的TaskId |**Yes**|
| **ReceiptSet** | array[[*ReceiptPerPhone*](#ReceiptPerPhone)] | 每个手机号的短信回执信息集合 |**Yes**|

#### ReceiptPerPhone

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SessionId** | string | SessionId |**Yes**|
| **Phone** | string | 手机号码 |**Yes**|
| **ReceiptResult** | string | 回执结果(发送成功、发送失败、状态未知) |**Yes**|
| **ReceiptCode** | string | 回执码 |**Yes**|
| **ReceiptDesc** | string | 回执结果描述 |**Yes**|
| **ReceiptTime** | int | 回执返回时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetISMSSendReceipt
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=YxpiUfMK
&TaskIdSet.N=nkVHwSwf
```

### 响应示例
    
```json
{
  "Action": "GetISMSSendReceiptResponse",
  "Data": [
    {
      "ReceiptSet": [
        "dvLbalts"
      ],
      "TaskId": "IubvXews"
    }
  ],
  "Message": "dqZhPBJi",
  "ReqUuid": "AqFSINSi",
  "RetCode": 0
}
```





