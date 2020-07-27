# 创建副本 - CreateUDBReplicationInstance

## 简介

创建MongoDB的副本节点（包括仲裁）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBReplicationInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBReplicationInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SrcId** | string | primary节点的DBId,该值可以通过DescribeUDBInstance获取 |**Yes**|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **Port** | int | 端口号，默认27017，取值范围3306至65535。 |No|
| **IsArbiter** | boolean | 是否是仲裁节点，默认false，仲裁节点按最小机型创建 |No|
| **UseSSD** | boolean | 是否使用SSD，默认 为 true |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | 创建从节点的DBId |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDBReplicationInstance
&Region=cn-bj2
&SrcId=udb-xxxxx
&Name=mongodb-xxxxxxx-01
```

### 响应示例
    
```json
{
  "Action": "CreateUDBReplicationInstanceResponse",
  "DBId": "udb-xxxxx",
  "RetCode": 0
}
```





