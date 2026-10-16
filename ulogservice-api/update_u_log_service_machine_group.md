# 更新日志机器组 - UpdateULogServiceMachineGroup

## 简介

更新日志机器组






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateULogServiceMachineGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateULogServiceMachineGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 机器组名称; 格式校验：^[<br />w]{1,255}$ |**Yes**|
| **Type** | string | 采集客户端识别模式;可选值 LABEL \| IP; |**Yes**|
| **Id** | int | 机器组ID |**Yes**|
| **Labels** | string | 采集客户端识别标识，数组类型 |No|
| **Ips** | string | 机器IP，如果Type是IP，那么Ips可以填写IP，是一个数组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateULogServiceMachineGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=JjTAlIfj
&InstanceId=qqYAzfKT
&GroupId=4
&GroupName=hUMnwQus
&IdentifyKeys.n=jQtfpLxi
&Id=5
```

### 响应示例
    
```json
{
  "Action": "UpdateULogServiceMachineGroupResponse",
  "Data": {},
  "Message": "BIPnncZH",
  "RetCode": 0
}
```





