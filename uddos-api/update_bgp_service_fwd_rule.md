# 修改BGP规则 - UpdateBGPServiceFwdRule

## 简介

用于修改BGP高防的规则信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateBGPServiceFwdRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateBGPServiceFwdRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 	<br />资源id |**Yes**|
| **BgpIP** | string | BGP的IP |**Yes**|
| **RuleIndex** | int | 要修改的规则index |**Yes**|
| **RuleID** | string | 规则uuid |**Yes**|
| **SourceAddrArr.N** | string | 回源地址,可填 IP地址 或 域名  |No|
| **SourcePortArr.N** | string | 回源端口 |No|
| **SourceToaIDArr.N** | string | 回源TOA |No|
| **LoadBalance** | string | 转发协议的类型是否为负载均衡的：默认为“No”，还可以选择为“Yes”。负载模式的规则最多添加2条，非负载模式的规则最多添加8条 |No|
| **FwdType** | string | 转发协议的类型包括三种：默认为“IP”，还可以选择为“TCP”或"UDP" |No|
| **BgpIPPort** | int | 默认为0，为IP协议的转发端口，其余的自定义 |No|
| **SourceDetect** | int | 表示对源站进行检测：默认为0表示关闭，还可以选择为1表示开启 |No|
| **BackupIP** | string | 备份源站的IP |No|
| **BackupPort** | int | 备份源站的端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleIndex** | int | 转发规则的数据库索引 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateBGPServiceFwdRule
&ResourceId="20b56aca-81b1-497d-86e8-aa7d02d67289"
&BgpIP="10.5.12.3"
&RuleID="djnfiw-jf9iwenfkd-37ndj"
&LoadBalance="Yes"
&FwdType="IP"
&BgpIPPort=80
&SourceDetect=1
&BackupIP="10.5.12.6"
&BackupPort=80
&BackupToa=200
&RuleID=wipOcbWY
&RuleIndex=6
&SourceAddrArr.0=1.1.1.1
&SourcePortArr.0=0
&SourceToaIDArr.0=200
```

### 响应示例
    
```json
{
  "Action": "UpdateBGPServiceFwdRuleResponse",
  "RetCode": 0,
  "RuleID": "qrJtPewi-7j9dfkjd-fdjj9"
}
```





