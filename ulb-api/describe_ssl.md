# 获取SSL证书信息 - DescribeSSL

## 简介

获取SSL证书信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSSL)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSSL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **SSLId** | string | SSL证书的Id |No|
| **Limit** | int | 数据分页值，默认为20 |No|
| **Offset** | int | 数据偏移量，默认值为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的SSL证书总数 |No|
| **DataSet** | array[[*ULBSSLSet*](#ULBSSLSet)] | SSL证书详细信息，具体结构见 ULBSSLSet |No|

#### 数据模型


#### ULBSSLSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | SSL证书的Id |No|
| **SSLName** | string | SSL证书的名字 |No|
| **SSLType** | string | SSL证书类型，暂时只有 Pem 一种类型 |No|
| **SSLContent** | string | SSL证书的内容 |No|
| **CreateTime** | int | SSL证书的创建时间 |No|
| **SSLBindedTargetSet** | array[[*SSLBindedTargetSet*](#SSLBindedTargetSet)] | SSL证书绑定到的对象 |No|

#### SSLBindedTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VServerId** | string | SSL证书绑定到的VServer的资源ID |No|
| **VServerName** | string | 对应的VServer的名字 |No|
| **ULBId** | string | VServer 所属的ULB实例的资源ID |No|
| **ULBName** | string | ULB实例的名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSSL
&Region=cn-bj2
&ProjectId=project-XXXXXX
```

### 响应示例
    
```json
{
  "Action": "DescribeSSLResponse",
  "DataSet ": [
    {
      "CreateTime": 1418099063,
      "HashValue": "1d5da9cf215d7c0e7b41b85af8adac2b",
      "SSLContent": "-----BEGIN RSA PRIVATE KEY-----\nXXXXXXXXXXXXX\n-----END CERTIFICATE-----",
      "SSLId": "ssl-XXXXX",
      "SSLName": "testpem",
      "SSLType": "Pem",
      "VServerId": ""
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





