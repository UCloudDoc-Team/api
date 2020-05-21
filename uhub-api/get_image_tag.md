# 获取镜像tag - GetImageTag

## 简介

获取镜像tag






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetImageTag)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetImageTag`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **RepoName** | string | 镜像仓库名称 |**Yes**|
| **ImageName** | string | 镜像名称 |**Yes**|
| **Offset** | int | 偏移量，默认0 |No|
| **Limit** | int | 每次获取数量，默认为20 |No|
| **TagName** | string | 默认不写，如果填写，代表查询该tag，否则查全部tag |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | tag总数 |**Yes**|
| **TagSet** | array[[*TagSet*](#TagSet)] | tag列表 |**Yes**|

#### 数据模型


#### TagSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UpdateTime** | string | 镜像更新时间 |**Yes**|
| **TagName** | string | Tag名称 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetImageTag
&ProjectId=PYFWFOHm
&RepoName=ZPGYodrQ
&ImageName=EpDfWhyI
&Offset=4
&Limit=6
&ProjectId=EiCgAvZy
&TagName=mBJNxhdo
```

### 响应示例
    
```json
{
  "Action": "GetImageTagResponse",
  "RetCode": 0,
  "TagSet": [
    {
      "TagName": "WAIUkrwN",
      "UpdateTime": "JuCcdSiy"
    },
    {
      "TagName": "cMPKnfJc",
      "UpdateTime": "uCNRUKaI"
    }
  ],
  "TotalCount": 3
}
```





