# 获取域名观众在线人数 - GetDomainPlayOnline

## 简介

获取域名观众在线人数






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetDomainPlayOnline)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetDomainPlayOnline`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询流量的起始时间，格式：时间戳 |**Yes**|
| **EndTime** | int | 查询流量的结束时间，格式：时间戳 |**Yes**|
| **DomainId.N** | string | 域名ID，创建域名时生成的ID，不传则获取所有 |No|
| **Domain.N** | string | 域名，不传则取所有播放域名 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **OnlineSet** | array[[*OnlineSet*](#OnlineSet)] | 观众在线数据列表，具体参考下面OnlineSet |No|
| **MaxOnline** | int | 观众在线峰值 |No|

#### 数据模型


#### OnlineSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间点。格式：时间戳 |**Yes**|
| **Value** | int | 在线人数，单位:人 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetDomainPlayOnline
&DomainId.n=KDPUyIIi
&BeginTime=8
&EndTime=8
```

### 响应示例
    
```json
{
  "Action": "GetDomainPlayOnlineResponse",
  "MaxOnline": 8.73958,
  "OnlineSet": [
    {
      "Time": 7,
      "Value": 9.75731
    },
    {
      "Time": 8,
      "Value": 9.39785
    }
  ],
  "RetCode": 0
}
```





