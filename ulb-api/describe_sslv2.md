# 获取SSL证书信息 - DescribeSSLV2

## 简介

获取SSL证书信息，该接口可以同时获取SSL与传统型和应用型负载均衡监听器的绑定关系






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSSLV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSSLV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
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
| **DataSet** | array[[*SSLInfo*](#SSLInfo)] | SSL证书详细信息，具体结构见SSLInfo |No|

#### 数据模型


#### SSLInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | SSL证书的Id |No|
| **SSLName** | string | SSL证书的名字 |No|
| **SSLType** | string | SSL证书类型，暂时只有 Pem 一种类型 |No|
| **SSLContent** | string | SSL证书的内容 |No|
| **CreateTime** | int | SSL证书的创建时间 |No|
| **HashValue** | string | SSL证书的HASH值 |No|
| **Relations** | array[[*SSLRelation*](#SSLRelation)] | SSL绑定ULB和ALB的关系 |No|
| **SSLSource** | int | SSL证书来源，SSL证书来源，0代表证书来自于ULB平台，1代表证书来自于USSL平台 |No|
| **USSLId** | string | USSL证书平台的编号,只有当SSLSource为1时才出现 |No|
| **Domains** | string | SSL证书的域名 |No|
| **DNSNames** | string | SSL证书的扩展域名 |No|
| **NotBefore** | int | 证书颁发时间 |No|
| **NotAfter** | int | 证书过期时间 |No|

#### SSLRelation

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LoadBalancerId** | string | 负载均衡实例的ID |No|
| **LoadBalancerName** | string | 负载均衡实例的名称	 |No|
| **ListenerId** | string | 监听器的ID	 |No|
| **ListenerName** | string | 监听器的名称 |No|
| **IsDefault** | boolean | 是否为监听器默认SSL证书 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSSLV2
&Region=MugqZBZG
&ProjectId=EAolgCLw
&SSLId=gmehGNgp
&Limit=5
&Offset=9
```

### 响应示例
    
```json
{
  "Action": "DescribeSSLV2Response",
  "DataSet": [
    {
      "CreateTime": 9,
      "SSLBindedTargetSet": [
        "ngLEWbOi"
      ],
      "SSLContent": "suFedZgn",
      "SSLId": "wWpnuBzD",
      "SSLName": "FLDjCBnm",
      "SSLType": "iMInfAKH"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





