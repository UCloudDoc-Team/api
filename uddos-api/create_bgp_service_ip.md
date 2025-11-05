# 创建BGP高防IP - CreateBGPServiceIP

## 简介

分配一个BGP IP






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateBGPServiceIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateBGPServiceIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id，表示归属在哪个高防服务下 |**Yes**|
| **TypeIP** | string | ip的类型, 默认是TypeFree |No|
| **EIPRegion** | string | 高防IP对应机房（直连高防必须携带） |No|
| **Remark** | string | 备注,默认为空 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DefenceIP** | string | 分配的BGP高防IP的IP地址 |**Yes**|
| **Cname** | string | cname记录 |No|
| **IPId** | int | IPId |No|
| **EnableSwitch** | int | 是否热备份开启 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateBGPServiceIP
&ResourceId="f961c1bf-11b4-4a24-b875-f29a83e00cd5"
&BlockUDP=0
&BGPServiceIP=""
&TypeIP=NwlyBVad
&Region=uWDNbJlT
&Remark=rXxNuajf
```

### 响应示例
    
```json
{
  "Action": "CreateBGPServiceIPResponse",
  "BgpIP": "10.5.12.3",
  "Cname": "pLEZtibq",
  "EnableSwitch": "TBCzQeti",
  "IPId": "AZSDlgri",
  "RetCode": 0
}
```





