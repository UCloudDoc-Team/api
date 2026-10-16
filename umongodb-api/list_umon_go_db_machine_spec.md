# 获取UMongoDB支持机器类型列表 - ListUMongoDBMachineSpec

## 简介

获取UMongoDB支持机器类型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMongoDBMachineSpec)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMongoDBMachineSpec`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClassType** | string | 机型,如O |No|
| **DiskType** | string | 磁盘类型，如CLOUD_RSSD |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*MongodbMachineSpec*](#MongodbMachineSpec)] | 规格列表 |**Yes**|

#### 数据模型


#### MongodbMachineSpec

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClassType** | string | 规格类型;O \| N  |No|
| **DiskType** | array[string] | 磁盘类型;CLOUD_RSSD \| CLOUD_SSD \| LOCAL_SSD |No|
| **ComputeType** | array[[*MongodbMachineType*](#MongodbMachineType)] | 计算规格列表 |No|
| **DefaultMachineType** | [*MongodbMachineType*](#MongodbMachineType) | 默认规格 |No|

#### MongodbMachineType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MachineTypeId** | string | 机器类型ID o.mongo2m.medium，o.mongo2m.xlarge |**Yes**|
| **Description** | string | 配置简称  2C4G |**Yes**|
| **Cpu** | int | cpu核数 |**Yes**|
| **Memory** | int | 内存用量(GB) |**Yes**|
| **UHhostMachineType** | string | 机器类型，N/O |No|
| **Group** | string | 配置分组，2m , 4m |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMongoDBMachineSpec
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ynzFdIrt
&ClassType=O  N
&DiskType=imLmDmDT
```

### 响应示例
    
```json
{
  "Action": "ListUMongoDBMachineSpecResponse",
  "DataSet": [
    {
      "Cpu": 9,
      "Description": "gqpVxYqN",
      "Group": "MJEKyWSw",
      "MachineTypeId": "zvurmTfw",
      "Memory": 4,
      "UHhostMachineType": "JiPXjArf"
    }
  ],
  "RetCode": 0
}
```





