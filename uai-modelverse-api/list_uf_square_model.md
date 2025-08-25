# 查询模型广场数据 - ListUFSquareModel

## 简介

查询模型广场数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUFSquareModel)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUFSquareModel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ModelType** | string | 模型类型 |No|
| **Keyword** | string | 关键字 |No|
| **Offset** | int | 偏移量 |No|
| **Limit** | int | 每页数量 |No|
| **OrderBy** | string | 排序字段 |No|
| **Order** | string | 排序顺序，默认倒序 |No|
| **MaxModelLen.N** | int | 上下文长度，数组类型，可选值 [0,4096,16384,32768,131072,256000,262144,1048576] |No|
| **Language.N** | string | 语言，数组类型，可选值 ["chinese", "english"] |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |**Yes**|
| **SquareModels** | array[[*SquareModel*](#SquareModel)] | 广场模型 |**Yes**|

#### 数据模型


#### SquareModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 主键 |No|
| **Name** | string | 名称 |No|
| **SimpleDescribe** | string | 简要描述 |No|
| **Describe** | string | 详细描述 |No|
| **Language** | array[string] | 语言 |No|
| **MaxModelLen** | int | 模型长度 |No|
| **ModelType** | string | 模型类型 |No|
| **HfUpdateTime** | int | HuggingFace 更新时间 |No|
| **CreateAt** | int | 创建时间 |No|
| **UpdateAt** | int | 更新时间 |No|
| **SupportedCapabilities** | array[string] | 模型能力 |No|
| **Icon** | string | 图标 |No|
| **Pricing** | [*Pricing*](#Pricing) | 定价策略 |No|

#### Pricing

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Completion** | float | 输出定价 |No|
| **Prompt** | float | 提示词定价 |No|
| **Image** | float | 生图定价 |No|
| **Currency** | string | 币种 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUFSquareModel
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jeBXhvUY
&ModelType=ooGwbevC
&MaxModelLen=RntjYoVL
&Keyword=CwciILMu
&Language=nBzKikde
&Offset=3
&Limit=5
&OrderBy=mtKYCGmg
&Order=EHqJJScF
```

### 响应示例
    
```json
{
  "Action": "ListUFSquareModelResponse",
  "RetCode": 0,
  "SquareModels": [
    "RPQHcFey"
  ],
  "TotalCount": "QlXKGgmL"
}
```





