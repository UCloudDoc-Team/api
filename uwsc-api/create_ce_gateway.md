# 创建CE客户网关 - CreateCEGateway

## 简介

创建CE客户网关






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCEGateway)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCEGateway`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PopGwId** | string | 所属UWAN虚拟路由器资源ID |**Yes**|
| **PublicIp** | string | 客户自有公网IP |**Yes**|
| **IpType** | string | IP类型 枚举值：静态IP(Static) \| 动态IP(Dynamic) |**Yes**|
| **Name** | string | 资源名称 |No|
| **Remark** | string | 备注 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VPNId** | string | 客户网关资源 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCEGateway
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=EyJCscGm
&PopGwId=jGGPcwZv
&PublicIp=wOcybaDt
&Name=AUjKNTGx
&Remark=zWypIzQF
&IpType=oCYaAbnb
&IpType=WIkRSAyB
```

### 响应示例
    
```json
{
  "Action": "CreateCEGatewayResponse",
  "Message": "kVoJzcVk",
  "RetCode": 0,
  "VPNId": "GIppqKNr"
}
```





