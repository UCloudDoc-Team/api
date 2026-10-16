# 获取令牌列表 - ListURocketMQToken

## 简介

获取URocketMQ令牌列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListURocketMQToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TokenList** | array[[*TokenDetail*](#TokenDetail)] | Token配置数组 |**Yes**|
| **TotalCount** | int | Token总数 |**Yes**|

#### 数据模型


#### TokenDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AKSK** | [*AKSK*](#AKSK) | 密钥 |**Yes**|
| **TokenId** | string | 令牌ID |**Yes**|
| **TopicProducePerm** | string | Topic生产权限 |**Yes**|
| **TopicConsumePerm** | string | Topic消费权限 |**Yes**|
| **ServiceId** | string | 	<br />Service ID |**Yes**|
| **Name** | string | 令牌名称 |**Yes**|
| **Type** | string | 令牌类型 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|

#### AKSK

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccessKey** | string | 公钥 |**Yes**|
| **SecretKey** | string | 私钥 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListURocketMQToken
&Region=cn-zj
&ProjectId=hzcDQprq
&ServiceId=iTPdUcqm
&Limit=1
&Offset=8
```

### 响应示例
    
```json
{
  "Action": "ListURocketMQTokenResponse",
  "Message": "OdLGlqYH",
  "RetCode": 0,
  "TokenList": [
    {
      "AKSK": {},
      "CreateTime": 6,
      "ModifyTime": 7,
      "Name": "CjZnNgAO",
      "ServiceId": "buJzEhNa",
      "TokenId": "VwFKblMj",
      "TopicConsumePerm": "lzYGFXsI",
      "TopicProducePerm": "VDjCndCl",
      "Type": "Default"
    }
  ],
  "TotalCount": 6
}
```





