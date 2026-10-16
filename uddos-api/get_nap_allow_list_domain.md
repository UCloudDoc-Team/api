# 获取域名允许列表 - GetNapAllowListDomain

## 简介

获取域名允许列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNapAllowListDomain)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNapAllowListDomain`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **Domain** | string | 获取指定域名信息 |No|
| **DomainLike** | string | 域名模糊查找 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为1000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 列表总条目数 |**Yes**|
| **DomainList** | array[[*BlockAllowDomainEntry*](#BlockAllowDomainEntry)] | 域名允许列表 |**Yes**|

#### 数据模型


#### BlockAllowDomainEntry

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **CreateTime** | int | 创建时间戳，例如：1581991500 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **Status** | int | 状态；1：添加中，2：成功，3：删除中，4：失败，5：已删除 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNapAllowListDomain
&ResourceId=uUDYRKta
&Domain=ucloud.cn
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "GetNapAllowListDomainResponse",
  "DomainList": [
    {
      "CreateTime": 1597126079,
      "Domain": "ucloud.cn",
      "Remark": "",
      "Status": 2
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





