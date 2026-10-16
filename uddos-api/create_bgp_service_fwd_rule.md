# 创建BGP高防转发规则 - CreateBGPServiceFwdRule

## 简介

创建BGP高防转发规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateBGPServiceFwdRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateBGPServiceFwdRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id  |**Yes**|
| **BgpIP** | string | BGP的IP |**Yes**|
| **SourceType** | string | 回源类型，分 “IP”、“Domain” |No|
| **SourceAddrArr.N** | string | 回源地址，可填 IP地址 或 域名  |No|
| **SourcePortArr.N** | string | 回源端口 |No|
| **SourceToaIDArr.N** | string | 回源TOA |No|
| **LoadBalance** | string | 转发协议的类型是否为负载均衡的：默认为“No”，还可以选择为“Yes”。负载均衡模式下必须配置BackupIP |No|
| **FwdType** | string | 转发协议的类型包括三种：默认为“IP”，还可以选择为“TCP” |No|
| **BgpIPPort** | int | 默认为0，为IP协议的转发端口，其余的自定义 |No|
| **SourceDetect** | int | 表示对源站进行检测：默认为0表示关闭，还可以选择为1表示开启 |No|
| **BackupIP** | string | 备份源站的IP |No|
| **BackupPort** | int | 备份源站的端口 |No|
| **Remark** | string | 备注，默认为空 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleIndex** | int | 转发规则的数据库索引值 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateBGPServiceFwdRule
&ResourceId=ab3607ef-3fa8-4a6e-9872-33175f5612ba
&BgpIP=1.2.3.4
&SourceType=IP
&SourceAddrArr.0=1.2.3.4
&SourcePortArr.0=0
&SourceToaIDArr.0=200 
&LoadBalance=No
&FwdType=IP
&BgpIPPort=0
&BackupIP=10.12.12.12
&BackupPort=0
&BackupToa=9
&Remark=test
```

### 响应示例
    
```json
{
  "Action": "CreateBGPServiceFwdRuleResponse",
  "RetCode": 0,
  "RuleIndex": 6
}
```





