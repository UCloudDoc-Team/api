# 普通UDB切换为高可用 - SwitchUDBInstanceToHA

## 简介

普通UDB切换为高可用(只针对mysql5.5及以上版本SSD机型的实例) ，原db状态为WaitForSwitch时，调用该api； 对于NVMe机型的单点升级高可用，虽然也能使用PromoteUDBInstanceToHA再加上该操作，但是更建议直接调用新的API接口（SetUpHAWithExistingUDBInstance）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SwitchUDBInstanceToHA)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SwitchUDBInstanceToHA`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DBId** | string | 实例的Id,该值可以通过DescribeUDBInstance获取 |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，不填则按现在单点计费执行<br /> |No|
| **Quantity** | string | 购买时长，需要和 ChargeType 搭配使用，否则使用单点计费策略的值 |No|
| **Tag** | string | 业务组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | 切换后高可用db实例的Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SwitchUDBInstanceToHA
&Region=cn-bj2
&DBId=udb-xxx
&ChargeType=GFfPZuzb
&Quantity=EIwSDflg
&Tag=YgoEVhht
```

### 响应示例
    
```json
{
  "Action": "SwitchUDBInstanceToHAResponse",
  "DBId": "udbha-xxxxx",
  "RetCode": 0
}
```





