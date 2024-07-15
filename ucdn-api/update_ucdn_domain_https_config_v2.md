# https加速配置 - UpdateUcdnDomainHttpsConfigV2

## 简介

https加速配置，国内，国外一起配置(兼容全站加速域名)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUcdnDomainHttpsConfigV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUcdnDomainHttpsConfigV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 域名对应的资源Id |**Yes**|
| **HttpsStatusCn** | string | 开启或关闭加速 enable或disable  当加速区域含国内的时候，此参数为必传 |No|
| **HttpsStatusAbroad** | string | 开启或关闭加速 enable或disable<br /> 当加速区域含国外的时候，此参数为必传 |No|
| **CertName** | string | 证书名称，开启加速必传 |No|
| **CertId** | int | 证书id(可能是ucdn的id，也可能是ussl的id) |No|
| **CertType** | string | 证书类型 ucdn/ussl  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUcdnDomainHttpsConfigV2
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=iPYAffih
&Areacode=cn国内abroad国外
&DomainId=ImuXStLR
&HttpsStatus=enable开启 disable关闭
&CertName=GwQisyBE
&CertId=3
&CertType=bBGEZtGs
&IsDcdn=true
&HttpsStatusAbroad=FddMdKye
```

### 响应示例
    
```json
{
  "Action": "UpdateUcdnDomainHttpsConfigV2Response",
  "RetCode": 0
}
```





