# 编辑防护域名信息 - ModifyWafDomainHostInfo

## 简介

编辑防护域名信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyWafDomainHostInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SrcIP.N** | string | 源站IP信息 |**Yes**|
| **WorkRegions** | string | 工作区域，用户已购买区域的子集，以逗号分隔，如：cn-bj,cn-sh |**Yes**|
| **FullDomain** | string | 被编辑的域名,域名与记录ID必须选填一项 |**Yes**|
| **HTTPRedirection** | string | 使用HTTP跳转，YES是，NO否，只允许HTTPS:YES,HTTP:NO的情况下使用 |No|
| **CertificateID** | int | HTTPS证书编号 |No|
| **RealIPHeader** | string | 获取真实客户端地址字段，如对接CDN等其他代理时使用 |No|
| **WorkMode** | string | 工作模式，Defence:启用防护规则,Alarm:记录不拦截,Inactive:放行 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyWafDomainHostInfo
&ProjectId=org-xxx
&FullDomain=https://www.test.com
&SrcIP.0=1.2.3.4
&HTTPRedirection=NO
&WorkRegions=cn-gd
&CertificateID=901
```

### 响应示例
    
```json
{
  "Action": "ModifyWafDomainHostInfoResponse",
  "RetCode": 0
}
```





