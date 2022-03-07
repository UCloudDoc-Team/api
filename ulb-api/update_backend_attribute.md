# 更新后端实例属性 - UpdateBackendAttribute

## 简介

更新ULB后端资源实例(服务节点)属性



!> 报文转发的服务节点暂不支持修改 Port；BackendId 对应的是 AllocateBackend 返回的 BackendId 或者 DescribeULB/DescribeVServer 返回的 ULBBackendSet 结构体中的 BackendId


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateBackendAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateBackendAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 负载均衡资源ID |**Yes**|
| **BackendId** | string | 后端资源实例的ID(ULB后端ID，非资源自身ID) |**Yes**|
| **Port** | int | 后端资源服务端口，取值范围[1-65535] |No|
| **Weight** | int | 所添加的后端RS权重（在加权轮询算法下有效），取值范围[0-100]，默认为1 |No|
| **Enabled** | int | 后端实例状态开关 |No|
| **IsBackup** | int | 是否为backup<br />0：主rs<br />1：备rs<br />默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateBackendAttribute
&Region=cn-bj2
&ProjectId=project-XXXX
&ULBId=ulb-XXXX
&BackendId=backend-XXXX
&Port=8080
&Enabled=0
&Weight=2
&IsBackup=0
```

### 响应示例
    
```json
{
  "Action": "UpdateBackendAttributeResponse",
  "BackendSet": [
    {
      "BackendId": "VrjEOOfp",
      "SubMessage": "fHpUyKqK",
      "SubRetCode": 1
    }
  ],
  "RetCode": 0
}
```





