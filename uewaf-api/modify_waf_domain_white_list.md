# 编辑域名白名单 - ModifyWafDomainWhiteList

## 简介

编辑域名白名单









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyWafDomainWhiteList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ID** | int | 要编辑的白名单记录ID |**Yes**|
| **FullDomain** | string | 该条记录所属的域名 |**Yes**|
| **CIDRS.N** | string | IP、网段或者IP段，传递数组 |No|
| **Remark** | string | 备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyWafDomainWhiteList
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=4
&CIDRS.0=2.2.2.3/31
&RecordId=8
&Remark=test
```

### 响应示例
    
```json
{
  "Action": "ModifyWafDomainWhiteListResponse",
  "RetCode": 0
}
```





