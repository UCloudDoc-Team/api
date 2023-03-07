# 更新负载均衡属性 - UpdateULBAttribute

## 简介

更新ULB名字业务组备注等属性字段






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateULBAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateULBAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | ULB资源ID |**Yes**|
| **Name** | string | 名字，不传则默认不修改 |No|
| **Tag** | string | 业务，不传则默认不修改 |No|
| **Remark** | string | 备注，不传则默认不修改 |No|
| **EnableLog** | int | 日志开关，1代表开启日志，0代表关闭日志，传1时必须同时传BucketName，TokenName与TokenId二选一 |No|
| **BucketName** | string | 设置用于存储ulb日志的bucket |No|
| **TokenName** | string | 用于指定上传到bucket所需的token，与TokenId选填其一即可 |No|
| **TokenId** | string | 用于指定上传到bucket所需的token，与TokenName选填其一即可 |No|
| **IsWAFOn** | string | 是否开启WAF。枚举类型：Yes，No，默认值为No |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateULBAttribute
&Region=cn-bj2
&ProjectId=project-XXXX
&ULBId=ulb-XXXX
&Name=test
&Tag=test
&Remark=test
&EnableLog=4
&BucketName=vDcQKdYV
&TokenName=KKdfUrIJ
&TokenId=USFJSFIY
&IsWAFOn=obMkyjOy
```

### 响应示例
    
```json
{
  "Action": "UpdateULBAttributeResponse",
  "RetCode": 0
}
```





