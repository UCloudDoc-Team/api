# 获取计划删除密钥列表 - ListScheduleDeletionKeys

## 简介

获取计划删除密钥列表，调用ScheduleKeyDeletion命令后进入此列表， 默认30天后正式删除。正式删除前可调用CancelScheduleKeyDeletion恢复






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListScheduleDeletionKeys)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListScheduleDeletionKeys`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 输出列表起始位置，默认从0开始 |No|
| **Limit** | int | 输出列表数量，默认返回200个 |No|
| **OrderBy** | string | 列表排序方式, 可选项: "-created_time", "created_time","plan_delete_time","-plan_delete_time";默认按-plan_delete_time 计划删除时间升序返回 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Objects** | array[[*CMK*](#CMK)] | 主密钥信息组成的列表 |**Yes**|
| **Status** | string | 操作结果 |No|
| **RequestUuid** | string | 请求唯一标识符 |No|
| **TotalCount** | int | 符合条件的总数, 不同于Limit |No|

#### 数据模型


#### CMK

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | CMK 的唯一标识符 |**Yes**|
| **Type** | string | 密钥类型，仅支持UCloudManagedKeys、CustomerManagedKeys。默认值CustomerManagedKeys |**Yes**|
| **Description** | string | 对密钥的描述说明 |**Yes**|
| **Enabled** | boolean | 是否启用 |**Yes**|
| **CreatedTime** | int | 创建时间 时间戳 |**Yes**|
| **LastModifiedTime** | int | 最后修改时间 时间戳 |**Yes**|
| **Alias** | string | 别名，与CMK一一对应 |No|
| **PlanDeleteTime** | int | 计划删除时间 时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListScheduleDeletionKeys
&ProjectId=tHNjmJFy
&Offset=2
&Limit=1
&OrderBy=fmNDDFOg
```

### 响应示例
    
```json
{
  "Action": "ListScheduleDeletionKeysResponse",
  "Objects": [
    {
      "CreatedTime": 2,
      "Description": "JZLFkWFu",
      "Enabled": true,
      "KeyId": "ukms-xxxx",
      "LastModifiedTime": 3
    }
  ],
  "RequestUuid": "31232123-xxxx-eyy455",
  "RetCode": 0,
  "Status": "success",
  "TotalCount": 8
}
```





