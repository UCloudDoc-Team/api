# 更新入口白名单 - UpdatePathXWhitelist

## 简介

更新入口白名单,仅限GlobalSSH 实例使用。其他uga-实例不生效






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdatePathXWhitelist)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdatePathXWhitelist`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | GlobalSSH实例ID，资源唯一标识 |**Yes**|
| **Whitelist.N** | string | 白名单规则,例如 "Whitelist.0": "192.168.1.1/24\|tcp\|22"，"Whitelist.1": "192.168.1.2\|tcp\|8080:8090"，第一个参数为ip或ip段，第二个参数代表协议（tcp/udp），第三个参数代表端口号或端口范围（使用 ':' 隔开）；可以添加多条规则（递增Whitelist.n字段内的n值）；此接口需要列出全部规则，例如不填则为清空白名单规则，如若需要增量添加，使用InsertPathXWhitelist接口,globalssh 没有端口范围：端口设置成加速端口，协议设置成tcp:ip\|tcp\|加速端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdatePathXWhitelist
&ProjectId=org-xxx
&InstanceId=uga-xxxx
&Whitelist.0=1.1.1.1|tcp|22
&Whitelist.1=192.168.1.1/24|tcp|22
&Whitelist.2=2.2.2.2|tcp|22
```

### 响应示例
    
```json
{
  "Action": "UpdatePathXWhitelistResponse",
  "Message": "",
  "RetCode": 0
}
```





