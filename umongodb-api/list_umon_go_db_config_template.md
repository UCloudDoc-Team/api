# 拉取配置模板 - ListUMongoDBConfigTemplate

## 简介

拉取配置模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMongoDBConfigTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMongoDBConfigTemplate`                        | **Yes** |
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
| **DataSet** | array[[*ConfigTemplate*](#ConfigTemplate)] | 配置模板列表 |**Yes**|

#### 数据模型


#### ConfigTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateId** | string | 模板ID |No|
| **TemplateName** | string | 模板名称 |No|
| **MongodbVersion** | string | mongo版本 |No|
| **ClusterType** | string | 集群类型 |No|
| **TemplateType** | string | 模板类型 UsersTemplate DefaultTemplate |No|
| **CreateTime** | int | 创建时间 |No|
| **ModifyTime** | int | 修改时间 |No|
| **DeleteTime** | int | 删除时间 |No|
| **Description** | string | 模板描述 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMongoDBConfigTemplate
&Region=cn-zj
&ProjectId=KcWyOTpE
```

### 响应示例
    
```json
{
  "Action": "ListUMongoDBConfigTemplateResponse",
  "DataSet": [
    {
      "ClusterType": "tfPvRgzA",
      "CreateTime": 7,
      "DeleteTime": 5,
      "Description": 9,
      "ModifyTime": 8,
      "MongodbVersion": "SOTymeGF",
      "TemplateId": "TgbWNpkG",
      "TemplateName": "RFFuHJKR",
      "TemplateType": "WvyshOce"
    }
  ],
  "Message": "DzwqjoYl",
  "RetCode": 0
}
```





