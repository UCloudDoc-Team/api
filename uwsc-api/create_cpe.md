# 创建 CPE - CreateCPE

## 简介

创建 CPE






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCPE)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCPE`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | cpe 名称 |**Yes**|
| **Remark** | string | cpe 备注 |**Yes**|
| **DeviceType** | string | 设备型号，枚举值: UCPE3600、UCPE3601 |**Yes**|
| **Label** | string | 标签：UReach智能网关：Access |No|
| **UserInfo** | string | 结构体，详见UserInfo模型 |No|
| **Count** | int | 数量，默认为1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CPEId** | string | cpe id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCPE
&ProjectId=OZbYVLLp
&RequestID=VoxEBreF
&Name=NyJDNyqF
&Remark=XyfwUbAe
&CouponId=KShqXMud
&DeviceType=sgCyphCa
&Label=SbfAjvIQ
&UserInfo=bStZuzxw
&Count=1
```

### 响应示例
    
```json
{
  "Action": "CreateCPEResponse",
  "CPEId": "WoDJavPb",
  "Message": "eVVejVIJ",
  "RetCode": 0
}
```





