# 创建统一接入加速实例端口 - CreateUGA3Port

## 简介

创建统一接入加速实例端口，目前仅支持四层TCP端口






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGA3Port)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGA3Port`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 加速配置实例ID |**Yes**|
| **TCP.N** | int | TCP接入端口，禁用65123端口 |No|
| **TCPRS.N** | int | TCP回源端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGA3Port
&ProjectId=KfqTCoLY
&InstanceId=HAklVUew
&HTTPHTTP.n=6
&HTTPHTTPRS.n=2
&HTTPSHTTP.n=1
&HTTPSHTTPRS.n=8
&HTTPSHTTPS.n=8
&HTTPSHTTPSRS.n=3
&TCP.n=3
&TCPRS.n=4
&UDP.n=4
&UDPRS.n=4
&WSWS.n=3
&WSWSRS.n=1
&WSSWSS.n=7
&WSSWSSRS.n=2
&WSSWS.n=5
&WSSWSRS.n=1
```

### 响应示例
    
```json
{
  "Action": "CreateUGA3PortResponse",
  "Message": "TcZyqDji",
  "RetCode": 0
}
```





