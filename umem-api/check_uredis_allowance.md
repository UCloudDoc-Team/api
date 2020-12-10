# 检查URedis资源是否足够 - CheckURedisAllowance

## 简介

检查主备Redis的资源是否足够创建新实例，以及主备Redis的扩容资源预检查






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CheckURedisAllowance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CheckURedisAllowance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 创建实例的容量大小, 单位:GB 目前仅支持1/2/4/8/16/32六种规格；扩缩容时，表示实例的目标资源大小 |**Yes**|
| **Count** | int | 创建实例的数量，[1-10] |**Yes**|
| **Protocol** | string |  |No|
| **RegionFlag** | boolean | 是否是跨机房URedis(默认false) |No|
| **GroupId** | string | 资源ID，扩容实例资源时的必传参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Count** | int | 创建实例资源时，表示可创建的数量；扩容资源时，返回1表示可以扩容，0表示可用区资源不足不能扩容 |**Yes**|
| **NeedMigrate** | boolean | 返回为True时，表示需要迁移；为Flase时表示无需迁移 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CheckURedisGroupAllowance
&Region=cn-north-02
&Size=4
&Count=5
&Protocol=abZKbHGn
&ProjectId=FGVllQOD
&GroupId=ulMxTJes
&GroupId=PdvxcmWj
&GroupId=zwUdMzBb
```

### 响应示例
    
```json
{
  "Action": "CheckURedisAllowanceResponse",
  "Count": 4,
  "NeedMigrate": false,
  "RetCode": 0
}
```





