# 查询分布式redis备份 - DescribeUMemBackup

## 简介

查询分布式redis备份






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemBackup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SpaceId** | string | 资源id |**Yes**|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 分页显示的条目数, 默认值为10 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UMemBackupSet*](#UMemBackupSet)] | 分布式redis 备份，数组的每个元素为每个分片的备份 |No|

#### 数据模型


#### UMemBackupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackupName** | string | 备份名称 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **State** | string | Starting:备份中 Done:完成 |**Yes**|
| **BackupId** | string | 空间的备份ID |**Yes**|
| **BackupType** | string | 备份类型: auto(自动) ,manual(手动) |**Yes**|
| **BlockCount** | int | 本次备份，分片的数量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemBackup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ttzQIEAS
&SpaceId=UgIbZdcJ
&Offset=3
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemBackupResponse",
  "DataSet": [
    {
      "BackupId": "YKTpXALa",
      "BackupName": "wswsYgCj",
      "BackupType": "XkJRGPby",
      "CreateTime": 3,
      "Protocol": "ADqlSMfS",
      "SpaceId": "BockWwNG",
      "State": "gvqEneLQ"
    }
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





