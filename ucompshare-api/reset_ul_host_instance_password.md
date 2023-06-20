# 重置轻量应用云主机密码 - ResetULHostInstancePassword

## 简介

重置轻量应用云主机管理员密码。



!> 该操作需要UHost实例处于关闭状态。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResetULHostInstancePassword`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ULHostId** | string | ULHost实例ID |**Yes**|
| **Password** | string | ULHost新密码（密码格式使用BASE64编码） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ULHostId** | string | ULHost实例ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResetULHostInstancePassword
&Region=cn-zj
&ProjectId=CAUPAisq
&ULHostId=jCauOLoz
&Password=AgZVFGfu
```

### 响应示例
    
```json
{
  "Action": "ResetULHostInstancePasswordResponse",
  "RetCode": 0,
  "ULHostId": "NcJIRRyi"
}
```




