# 获取UDBbinlog列表 - DescribeUDBInstanceBinlog

## 简介

获取UDB指定时间段的binlog列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBInstanceBinlog)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBInstanceBinlog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DBId** | string | DB实例Id |**Yes**|
| **BeginTime** | int | 过滤条件:起始时间(时间戳) |**Yes**|
| **EndTime** | int | 过滤条件:结束时间(时间戳) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBInstanceBinlogSet*](#UDBInstanceBinlogSet)] | 获取的Binlog信息列表 UDBInstanceBinlogSet |No|

#### 数据模型


#### UDBInstanceBinlogSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | Binlog文件名 |No|
| **Size** | int | Binlog文件大小 |No|
| **BeginTime** | int | Binlog文件生成时间(时间戳) |No|
| **EndTime** | int | Binlog文件结束时间(时间戳) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceBinlog
&Region=cn-bj2
&DBId=2bbf9968-2ded-48c5-89c0-4f4d683bdd6c
&BeginTime=1432569600
&EndTime=1432588600
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBInstanceBinlogResponse",
  "DataSet": [
    {
      "BeginTime": 1432698250,
      "EndTime": 1432698250,
      "Name": "mysql-bin.000004",
      "Size": 67543
    },
    {
      "BeginTime": 1432699250,
      "EndTime": 1432699250,
      "Name": "mysql-bin.000005",
      "Size": 67292
    }
  ],
  "RetCode": 0
}
```





