# 绑定高防IP资源 - BindNapIP

## 简介

直连高防：将尚未使用的高防EIP绑定到指定的资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BindNapIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BindNapIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ResourceId** | string | 高防资源ID |**Yes**|
| **EIPId** | string | EIP资源ID |**Yes**|
| **ResourceType** | string | 绑定的资源类型(uhost:云主机,ulb:负载均衡,upm:物理机) |**Yes**|
| **NapIp** | string | 高防IP |**Yes**|
| **BindResourceId** | string | 绑定的资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BindNapIP
&ProjectId=aCNkkrfS
&TopOrganizationId=8
&OrganizationId=3
&AzGroup=9
&EIPId=RIlSfcRG
&ResourceType=HTErNBas
&ResourceId=EIPPySbz
&BindResouceId=KSMvpqfN
&NapIp=XinUjLhQ
```

### 响应示例
    
```json
{
  "Action": "BindNapIPResponse",
  "Message": "HjddYOjn",
  "RetCode": 0
}
```





