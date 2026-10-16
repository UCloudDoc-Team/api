# 获取域名基本信息 - GetUcdnDomainInfoList

## 简介

获取域名基本信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainInfoList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainInfoList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PageSize** | int | 分页的大小，不填默认每页20个 |No|
| **PageIndex** | int | 返回第几页，序号从1开始，不填默认是第1页，填0表示不用分页直接返回所有数据 |No|
| **QueryByProject** | boolean | 是否按项目查询，true  或 false  <br />默认为false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 账户下域名总个数 |**Yes**|
| **DomainInfoList** | array[[*DomainBaseInfo*](#DomainBaseInfo)] | 域名基本信息 |**Yes**|

#### 数据模型


#### DomainBaseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **DomainId** | string | 域名的资源id |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnDomainInfoList
&ProjectId=FbIiIwSw
&PageSize=2
&PageIndex=1
&QueryByProject=false
```

### 响应示例
    
```json
{
  "Action": "GetUcdnDomainInfoListResponse",
  "DomainInfoList": [
    {
      "Domain": "xx.ucloud.com",
      "DomainId": "ucdn-asdHd3lj"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





