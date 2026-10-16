# 修改弹性IP出口权重 - ModifyEIPWeight

## 简介

修改弹性IP的外网出口权重

?> 本接口只针对EIP绑定主机或网卡(非直通模式下)资源时有效




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyEIPWeight)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyEIPWeight`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **EIPId** | string | 弹性IP的资源ID |**Yes**|
| **Weight** | int | 外网出口权重，范围[0-100]；该权重值只在EIP绑定资源为主机/网卡(非直通模式)时有效；同一个主机/网卡主动访问外网时，将使用权重最高的EIP作为源IP；权重相同时，行为不确定 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyEIPWeight
&Region=cn-bj2
&EIPId=eip-XXXXX
&Weight=4
```

### 响应示例
    
```json
{
  "Action": "ModifyEIPWeightResponse",
  "Request_uuid": "aad2bbf8-b12e-4057-83dd-XXXXXX",
  "RetCode": 0
}
```





