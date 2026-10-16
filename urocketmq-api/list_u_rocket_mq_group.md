# 获取 Group 列表 - ListURocketMQGroup

## 简介

获取一个 RocketMQ 服务下的所有 Group









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListURocketMQGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Limit** | int | 最多返回的条目数量, (0, 1000], 默认 50 条 |No|
| **Offset** | int | 查询起始位置, [0, ∞) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupList** | array[[*GroupBaseInfo*](#GroupBaseInfo)] | Group列表信息 |No|
| **TotalCount** | int | 记录总数 |No|

#### 数据模型


#### GroupBaseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | Group ID |**Yes**|
| **GroupName** | string | Group 名称 |**Yes**|
| **Remark** | string | Group 描述 |**Yes**|
| **CreateTime** | int | Group 创建时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListURocketMQGroup
&Region=cn-zj
&ProjectId=uUQrxcmz
&ServiceId=XRkCLnKy
&Limit=100
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "ListURocketMQGroupResponse",
  "ConsumerGroupList": [
    {
      "CreateTime": 1618318932,
      "GroupName": "apzNcABI",
      "Id": "ZABVgTBC",
      "Remark": "Diuxsbmn"
    }
  ],
  "Message": "qCIwrpbX",
  "RetCode": 0,
  "TotalCount": 1
}
```





