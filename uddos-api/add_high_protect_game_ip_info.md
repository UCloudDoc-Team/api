# 添加代理ip - AddHighProtectGameIPInfo

## 简介

添加代理ip






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddHighProtectGameIPInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddHighProtectGameIPInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源Id |**Yes**|
| **TypeIP** | string | IP类型,取值范围为:TypeFree,  TypeCharge |**Yes**|
| **UserIP** | string | 用户的源站ip |**Yes**|
| **LineType** | string | 套餐线路类型, 如果是BGP的线路, 则为BGP;如果为双线, 则可选TELECOM, UNICOM;如果为海外, 则为INTERNATIONAL; |**Yes**|
| **Remark** | string | 备注,默认为空. |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DefenceIP** | string | 防御IP |**Yes**|
| **SrcIP** | string | 源IP |**Yes**|
| **Cname** | string | cname记录 |**Yes**|
| **IPId** | int | IPId |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddHighProtectGameIPInfo
&ProjectId=vYBpILpM
&ResourceId="83cef490-2176-4a05-8631-2a7f17febd73"
&TypeIP="TypeFree"
&UserIP=1.2.3.4
&Remark="test"
&CouponId="6c347e61"
&LineType="DUPLET"
&UdpBlock=1
&DefenceDDosMaxFlow=10
```

### 响应示例
    
```json
{
  "Action": "AddHighProtectGameIPInfoResponse",
  "Cname": "jdhfh.6cname.cn",
  "DefenceIP": "10.10.10.1",
  "IPId": "",
  "RetCode": 0,
  "SrcIP": "1.1.1.1"
}
```





