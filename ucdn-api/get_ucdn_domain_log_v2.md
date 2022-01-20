# 获取域名5分钟日志 - GetUcdnDomainLogV2

## 简介

获取域名5分钟日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainLogV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainLogV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp |**Yes**|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DomainLogSet** | array[[*DomanLogList*](#DomanLogList)] |  |**Yes**|

#### 数据模型


#### DomanLogList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |No|
| **LogList** | array[[*LogInfo*](#LogInfo)] | 日志信息列表 |No|

#### LogInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LogTime** | int | Unix时间戳 |**Yes**|
| **LogUrl** | string | 日志url地址 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnDomainLogV2
&ProjectId=jtlEEXGE
&BeginTime=1
&EndTime=8
&DomainId.n=ziMJIfEj
```

### 响应示例
    
```json
{
  "Action": "GetUcdnDomainLogV2Response",
  "DomainLogSet": [
    {
      "Domain": "QvsyjlbW",
      "LogList": [
        {
          "LogTime": 4,
          "LogUrl": "NhGLRDgK"
        }
      ]
    }
  ],
  "RetCode": 0
}
```





