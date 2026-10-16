# 获取UPgSQL支持机器类型列表 - ListUPgSQLMachineType

## 简介

获取UPgSQL支持机器类型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUPgSQLMachineType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUPgSQLMachineType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*PgSQLMachineType*](#PgSQLMachineType)] |  |**Yes**|

#### 数据模型


#### PgSQLMachineType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 机器类型ID |No|
| **Description** | string | 格式为nCmG,n代表cpu核数，m代表内存大小(GB) |No|
| **Cpu** | int | cpu核数 |No|
| **Memory** | int | 内存用量(GB)  |No|
| **Os** | string | 机器类型，N/O |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUPgSQLMachineType
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=QuQgqZvr
```

### 响应示例
    
```json
{
  "Action": "ListUPgSQLMachineTypeResponse",
  "DataSet": [
    {
      "Cpu": 8,
      "Description": "yTviIpKc",
      "ID": "raOduvWd",
      "Memory": 5,
      "Os": "aziohbtn"
    }
  ],
  "Message": "lrXZBmKE",
  "RetCode": 0
}
```





