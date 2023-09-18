# 回档指定库表 - RollbackUDBInstance

## 简介

在原实例回档指定库表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=RollbackUDBInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RollbackUDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **SrcDBId** | string | 源实例的Id |**Yes**|
| **RecoveryTime** | string | 恢复到某个时间点的时间戳(UTC时间格式，默认单位秒) |**Yes**|
| **Tables** | string | 指定需要恢复的表，格式为(库名.表名)， 指定多个用逗号隔开，eg: [ udb.test, mysql_school.my_student] |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | 源实例的Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RollbackUDBInstance
&Region=cn-zj
&SrcDBId=MQGXvuLc
&RecoveryTime=SYFHrhPd
&Tables=GcrbXXIC
```

### 响应示例
    
```json
{
  "Action": "RollbackUDBInstanceResponse",
  "DBId": "udbha-toayxUOA",
  "RetCode": 0
}
```





