# 新增防护域名配置 - AddWafDomainHostInfo

## 简介

新增防护域名配置





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddWafDomainHostInfo)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafDomainHostInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 	<br />项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要防护的域名 |**Yes**|
| **WorkRegions** | string | 工作区域，用户已购买区域的子集，以逗号分隔，如：cn-bj,cn-sh |**Yes**|
| **WorkMode** | string | 工作模式，Defence:启用防护规则,Alarm:记录不拦截,Inactive:放行；默认Alarm |No|
| **SrcIP.N** | string | 源站IP端口信息，格式为：http://192.168.1.1或http://192.168.1.1:80；兼容http:192.168.1.1:80，支持CNAME |No|
| **CertificateID** | int | HTTPS证书编号，源站前缀为https时必填 |No|
| **HTTPRedirection** | string | 使用HTTP跳转，YES是，NO否，只允许HTTPS:YES,HTTP:NO的情况下使用且只配置了https 443端口的源站 |No|
| **ExclusiveIP** | string | 标识该域名使用独享防御IP，YES是，NO否；启用将为改域名分配一个独享防御IP |No|
| **RealIPHeader** | string | 获取真实客户端地址字段，如对接CDN等其他代理时使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功后返回的域名配置ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafDomainHostInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
&WorkRegions=cn-gd
&SrcIPNum=1
&SrcIP.0=http://106.75.66.11:80
&CertificateID=0
&ExclusiveIP=No
```

### 响应示例
    
```json
{
  "Action": "AddWafDomainHostInfoResponse",
  "Id": 9,
  "RetCode": 0
}
```





