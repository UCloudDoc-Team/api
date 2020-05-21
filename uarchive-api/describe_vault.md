# 获取Vault信息 - DescribeVault

## 简介

获取Vault信息

?> 特别说明:<br />VaultName参数必须符合Vault名称规范,规范如下: (1) 长度在3\~63字节之间； (2) 可以由多个标签组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结尾的字符只能是小写字母或数字； (3) 不可以是IP地址。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVault)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVault`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不选择为默认项目，子帐号必选 |No|
| **VaultName** | string | 待获取Vault的名称，若不提供，则获取所有Vault |**Yes**|
| **Offset** | int | 获取所有Vault列表的偏移数目，默认为0 |No|
| **Limit** | int | 获取所有Vault列表的限制数目，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*VaultSet*](#VaultSet)] | Vault的描述信息 |No|

#### 数据模型


#### VaultSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VaultName** | string | Vault名称 |**Yes**|
| **VaultId** | string | Vault的ID |**Yes**|
| **Domain** | string | Vault的域名集合 |**Yes**|
| **CreateTime** | int | Vault的创建时间 |**Yes**|
| **ModifyTime** | int | Vault的修改时间 |**Yes**|
| **Region** | string | Vault所属地域 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn?Action=DescribeVault
&VaultName=blue
&Offset=0
&Limit=20
&ProjectId=cOoJjcam
```

### 响应示例
    
```json
{
  "Action": "DescribeVaultResponse",
  "DataSet": [
    {
      "CreateTime": 1468929616,
      "Domain": "robert-test.uarchive.ucloud.cn",
      "ModifyTime": 1468929616,
      "Region": "cn-bj",
      "VaultId": "uarchive-xxx",
      "VaultName": "robert-test"
    }
  ]
}
```





