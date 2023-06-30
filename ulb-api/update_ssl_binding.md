# 更换证书绑定关系 - UpdateSSLBinding

## 简介

将VServer绑定的证书更换为另一个证书

?> 目前接口灰度中，如有需求请联系技术支持




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateSSLBinding)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateSSLBinding`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **OldSSLId** | string | VServer实例绑定的旧的证书 |**Yes**|
| **NewSSLId** | string | VServer实例需要绑定的新的证书 |**Yes**|
| **LoadBalancerId** | string | 所操作ULB实例ID（仅LoadBalancerId传参时，将更换该ULB所有原证书为OldSSLId的绑定关系；LoadBalancerId和ListenerId都不传参则将更新该项目下所有原证书为OldSSLId的绑定关系） |No|
| **ListenerId** | string | 所操作VServer实例ID（仅ListenerId传参时，将更换该Vserver所有原证书为OldSSLId的绑定关系；LoadBalancerId和ListenerId都不传参则将更新该项目下所有原证书为OldSSLId的绑定关系；若LoadBalancerId与ListenerId皆有传参，则会强校验ULB与Vsserver的所属关系，将更换该ulb下vserver所绑定的OldSSLId为NewSSLId） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateSSLBinding
&Region=rlOKcLRx
&ProjectId=fFdbMoEE
&ULBId=pecWyopE
&VServerId=FvbeTLVk
&OldSSLId=CbnyEXQg
&NewSSLId=wezHQFgd
&ULBId=zEuiHKHC
&VServerId=fUAheFtz
&ULBId=WtoMKBTg
&VServerId=nMcQugdp
```

### 响应示例
    
```json
{
  "Action": "UpdateSSLBindingResponse",
  "RetCode": 0
}
```





