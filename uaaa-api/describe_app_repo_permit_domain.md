# 查询允许加速的域名白名单 - DescribeAppRepoPermitDomain

## 简介

查询允许加速的域名白名单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeAppRepoPermitDomain)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAppRepoPermitDomain`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*DomainDetail*](#DomainDetail)] | 加速域名白名单列表 |No|

#### 数据模型


#### DomainDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Info** | [*DomainInfo*](#DomainInfo) | 被加速域名 |**Yes**|
| **Redirect** | array[[*DomainInfo*](#DomainInfo)] | 被加速域名重定向的域名列表   |**Yes**|

#### DomainInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainName** | string | 域名解析记录名称 |No|
| **Desc** | string | 备注信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAppRepoPermitDomain
&Region=cn-bj2
&ProjectId=org-XXXXXX
```

### 响应示例
    
```json
{
  "Action": "DescribeAppRepoPermitDomainResponse",
  "DataSet": [
    {
      "Info": {
        "Desc": " ",
        "DomainName": "*.github.com"
      },
      "Redirect": [
        {
          "Desc": " ",
          "DomainName": "*.githubusercontent.com"
        }
      ]
    }
  ],
  "Message": "ZafcyvKD",
  "RetCode": 0
}
```





