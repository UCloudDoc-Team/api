# SQL样本分析 - GetUDACMySQLSlowLogSample

## 简介

SQL样本分析






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUDACMySQLSlowLogSample)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDACMySQLSlowLogSample`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceID** | string | 数据库实例ID |**Yes**|
| **SQLFingerprint** | string | SQL 模板内容 |**Yes**|
| **StartTime** | int | 开始时间戳 |**Yes**|
| **EndTime** | int | 结束时间戳 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SampleSQL** | string | SQL 样本 |**Yes**|
| **ExplainSQLInfoSet** | array[[*ExplainSQLInfo*](#ExplainSQLInfo)] | SQL 样本分析结果 |**Yes**|

#### 数据模型


#### ExplainSQLInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 记录ID |No|
| **SelectType** | string | 类型 |No|
| **Table** | string | 表明 |No|
| **ExplainType** | string | Explain 类型 |No|
| **Extra** | string | 包含关于查询执行的其他信息，如使用临时表、使用文件排序等 |No|
| **Rows** | int | 扫描行数 |No|
| **PossibleKeys** | string | 可能用于此查询的索引列表 |No|
| **Key** | string | 实际使用的索引 |No|
| **KeyLen** | string | 索引字段的最大长度 |No|
| **Ref** | string | 在 type 列中使用的索引的哪一列或常量与列比较 |No|
| **Filtered** | int | 结果集的行数在表的总行数中的比例 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDACMySQLSlowLogSample
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=epzOeoEd
&InstanceID=yCHoBCIM
&SQLFingerprint=itYCbWIg
&StartTime=4
&EndTime=3
```

### 响应示例
    
```json
{
  "Action": "GetUDACMySQLSlowLogSampleResponse",
  "ExplainSQLInfoSet": [
    {
      "ExplainType": "OoNoTxmU",
      "Extra": "WVaEQVcY",
      "Filtered": "oAlgfwMj",
      "ID": 8,
      "Key": "KajbwlEI",
      "KeyLen": 3,
      "PossibleKeys": "mqERqetX",
      "Ref": "jDPnwYvJ",
      "Rows": 7,
      "SelectType": "czYnWQtK",
      "Table": "YGhgGsai"
    }
  ],
  "RetCode": 0,
  "SampleSQL": "VqkEWIpf"
}
```





