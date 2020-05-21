# 获取镜像仓库 - GetRepo

## 简介

获取镜像仓库






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetRepo)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetRepo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Type** | string | private私有仓库，public公共仓库，默认public |No|
| **Offset** | int | 偏移量，默认0 |No|
| **Limit** | int | 数量，默认20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总的仓库数量 |**Yes**|
| **RepoSet** | array[[*RepoSet*](#RepoSet)] | 镜像仓库列表 |**Yes**|

#### 数据模型


#### RepoSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RepoName** | string | 镜像仓库名称 |**Yes**|
| **CreateTime** | string | 仓库创建时间 |**Yes**|
| **UpdateTime** | string | 仓库更新时间 |**Yes**|
| **Description** | string | 镜像仓库描述 |**Yes**|
| **IsShared** | string | 镜像仓库类型,false为私有；true为公有 |**Yes**|
| **IsOutSide** | string | 镜像仓库是否外网可以访问，可以为ture,不可以为false |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetRepo
&ProjectId=DPQzQxpe
&Type=EzVxntiX
&Offset=1
&Limit=3
&ProjectId=uhpPXDet
```

### 响应示例
    
```json
{
  "Action": "GetRepoResponse",
  "RepoSet": [
    "ntmEsbYx",
    "ORXeSVYD",
    "NLnhyWGk",
    "RjXuIDDg",
    "qrDktRNL",
    "aVhDFvep",
    "JvxMmIMA",
    "BlemVnAI",
    "uekjGZaL"
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





