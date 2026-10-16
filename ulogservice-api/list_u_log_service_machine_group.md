# 查看机器组列表 - ListULogServiceMachineGroup

## 简介

查看机器组列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListULogServiceMachineGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListULogServiceMachineGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineGroups** | array[[*MachineGroup*](#MachineGroup)] | 机器组信息列表 |**Yes**|

#### 数据模型


#### MachineGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 机器组ID |No|
| **Name** | string | 机器组名称 |No|
| **Type** | string | 采集器识别类型：LABEL：机器标识，IP：IP类型 |No|
| **CreateTime** | int | 创建时间 |No|
| **UpdateTime** | int | 修改时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListULogServiceMachineGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=oEUirnuh
&InstanceId=srGjEpwe
&CollectConfId=1
```

### 响应示例
    
```json
{
  "Action": "ListULogServiceMachineGroupResponse",
  "Data": [
    {
      "CreateTime": 5,
      "GroupName": "BiVWpAAk",
      "Id": 6,
      "IdentifyKeys": [
        "KudDBjhZ"
      ],
      "IdentifyType": "DdUFzaaK",
      "UpdateTime": 2
    }
  ],
  "Message": "LTBDNoDx",
  "RetCode": 0
}
```





