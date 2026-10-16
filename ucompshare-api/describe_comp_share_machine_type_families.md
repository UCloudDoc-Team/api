# 获取实例规格族列表（所有机型的信息） - DescribeCompShareMachineTypeFamilies

## 简介

获取实例规格族列表（所有机型的信息）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCompShareMachineTypeFamilies`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。因为子账号要iam鉴权而填写 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineTypes** | array[string] | 机型配置列表 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCompShareMachineTypeFamilies
&ProjectId=AyMgwTqt
```

### 响应示例
    
```json
{
  "Action": "DescribeCompShareMachineTypeFamiliesResponse",
  "MachineTypes": [
    "eZQXVIAM"
  ],
  "RetCode": 0
}
```





