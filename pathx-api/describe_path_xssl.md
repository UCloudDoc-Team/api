# 获取SSL证书信息 - DescribePathXSSL

## 简介

获取SSL证书信息,支持分页，支持按证书名称 证书域名模糊搜索






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePathXSSL)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePathXSSL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **SSLId** | string | SSL证书的Id，不传分页获取证书列表 |No|
| **SearchValue** | string | 不为空则按证书名称、证书域名模糊搜索 分页返回结果 |No|
| **Limit** | int | 最大返回条数，默认100，最大400 |No|
| **Offset** | int | 偏移值 默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*PathXSSLSet*](#PathXSSLSet)] | SSL证书详细信息，具体结构见 PathXSSLSet |No|
| **TotalCount** | int | 符合条件的证书总数 |No|

#### 数据模型


#### PathXSSLSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | SSL证书的Id |No|
| **SSLName** | string | SSL证书的名字 |No|
| **SubjectName** | string | 证书域名 |No|
| **ExpireTime** | int | 证书过期时间 时间戳 |No|
| **SourceType** | int | 证书来源，0：用户上传 1: 免费颁发 |No|
| **SSLMD5** | string | SSL证书（用户证书、私钥、ca证书合并）内容md5值 |No|
| **CreateTime** | int | SSL证书的创建时间 时间戳 |No|
| **SSLBindedTargetSet** | array[[*SSLBindedTargetSet*](#SSLBindedTargetSet)] | SSL证书绑定的对象 |No|
| **SSLContent** | string | SSL证书内容 |No|

#### SSLBindedTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | SSL证书绑定到的实例ID |**Yes**|
| **ResourceName** | string | SSL证书绑定到的实例名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePathXSSL
&ProjectId=org-xxx
&SSLId=gssl-xxxx
&SearchValue=
&Limit=10
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "DescribePathXSSLResponse",
  "DataSet": [
    {
      "CreateTime": 1580000001,
      "ExpireTime": 1590000001,
      "SSLBindedTargetSet": [
        {
          "ResourceId": "uga-xxx",
          "ResourceName": "testl7"
        }
      ],
      "SSLContent": "----BEGIN-----",
      "SSLId": "gssl-xxxx",
      "SSLMD5": "132321312323==",
      "SSLName": "test",
      "SubjectName": "www.uclouds.com"
    }
  ],
  "RetCode": 0,
  "TotalCount": 8
}
```





