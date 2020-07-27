# 邀请子帐号成员 - InviteSubaccount

## 简介

邀请子帐号成员






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=InviteSubaccount)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `InviteSubaccount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserEmail** | string | 受邀成员邮箱地址，不得重复 |**Yes**|
| **UserPhone** | string | 受邀成员手机号码 |**Yes**|
| **UserName** | string | 受邀成员姓名 |**Yes**|
| **IsFinance** | string | 是否有财务权限(true:是,false:否,默认为否) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=InviteSubaccount
&UserEmail=lOqBhhkG
&UserPhone=SBwrZBSY
&UserName=mdHhPdnD
&IsFinance=IvixWFse
```

### 响应示例
    
```json
{
  "Action": "InviteSubaccountResponse",
  "RetCode": 0
}
```





