# 获取配置模板内容 - GetUMongoDBCfgTempItem

## 简介

获取配置模板内容






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUMongoDBCfgTempItem)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMongoDBCfgTempItem`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TemplateId** | string | 配置模板Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*ConfigTemplateItem*](#ConfigTemplateItem)] | 配置模板项 |**Yes**|

#### 数据模型


#### ConfigTemplateItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ItemId** | string | itemId |No|
| **TemplateId** | string | 模板ID |No|
| **ConfigName** | string | 配置名称 |No|
| **ConfigValue** | string | 配置值 |No|
| **CreateTime** | int | 创建时间 |No|
| **ModifyTime** | int | 修改时间 |No|
| **ConfigOption** | [*ConfigOptions*](#ConfigOptions) | 配置选项 |No|
| **NodeType** | string | 节点类型: DataNode:数据节点 \| ConfigSrvNode:配置节点 \| MongosNode:路由节点 |No|

#### ConfigOptions

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MongodbVersion** | string | mongo版本 |No|
| **OptionName** | string | 配置选项名 |No|
| **OptionValueType** | string | 配置选项类型 string,int,bool |No|
| **OptionValues** | string | 配置选项值范围 |No|
| **OptionDefaultValue** | string | 默认值 |No|
| **IsDefaultOption** | boolean | 是否为默认选项 |No|
| **EnableModify** | boolean | 是否可修改 |No|
| **EnableDisplay** | boolean | 是否前端展示 |No|
| **ForceRestart** | boolean | 是否需重启 |No|
| **OptionFormatType** | string | 选项值格式 |No|
| **AllowedApplyType** | string | 允许应用类型 |No|
| **Description** | string | 描述 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMongoDBCfgTempItem
&Region=cn-zj
&ProjectId=jzhnMxWp
&TemplateId=LRRJpzCz
```

### 响应示例
    
```json
{
  "Action": "GetUMongoDBCfgTempItemResponse",
  "DataSet": [
    {
      "ConfigName": "WpTOsYvM",
      "ConfigOption": {},
      "ConfigValue": "BeQDjMdY",
      "CreateTime": 8,
      "ItemId": "ZltgIHYS",
      "ModifyTime": 4,
      "TemplateId": "UqQZTRIx"
    }
  ],
  "Message": "Dcxfnytk",
  "RetCode": 0
}
```





