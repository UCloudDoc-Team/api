# 查看主密钥 - DescribeKey

## 简介

查看主密钥信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考GetProjectList接口 |No|
| **KeyId** | string | 需要查看的主密钥对应的 KeyId |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyId** | string | CMK 的唯一标识符 |No|
| **Alias** | string | 别名 |No|
| **Description** | string | 对密钥的描述说明 |No|
| **Enabled** | boolean | 是否启用 |No|
| **CreatedTime** | int | 创建时间 |No|
| **LastModifiedTime** | int | 最后修改时间 |No|
| **Status** | string | API执行状态 |No|
| **RequestUuid** | string | API请求ID |No|
| **Type** | string | 密钥类型，如ucloud_manage、self_manage |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
```

### 响应示例
    
```json
{
  "Action": "DescribeKeyResponse",
  "Alias": "vKdnnfCj",
  "CreatedTime": 1,
  "Description": "jXLaGikX",
  "Enabled": true,
  "KeyId": "ukms-xxxx",
  "LastModifiedTime": 7,
  "RequestUuid": "093399-ssxbcbc-3423444",
  "RetCode": 0,
  "Status": "success",
  "Type": "CustomerManagedKeys"
}
```





