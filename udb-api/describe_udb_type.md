# 获取云数据库支持类型 - DescribeUDBType

## 简介

获取UDB支持的类型信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **BackupZone** | string | 跨可用区高可用DB的备库所在区域，仅当该可用区支持跨可用区高可用时填入。参见 [可用区列表](api/summary/regionlist) |No|
| **DBClusterType** | string | DB实例类型，如mysql，sqlserver，mongo，postgresql |No|
| **InstanceMode** | string | 返回支持某种实例类型的DB类型。如果没传，则表示任何实例类型均可。<br />normal:单点,ha:高可用,sharded_cluster:分片集群 |No|
| **DiskType** | string | 返回支持某种磁盘类型的DB类型，如Normal、SSD、NVMe_SSD。如果没传，则表示任何磁盘类型均可。 |No|
| **CompatibleWithDBType** | string | 返回从备份创建实例时，该版本号所支持的备份创建版本。如果没传，则表示不是从备份创建。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBTypeSet*](#UDBTypeSet)] | DB类型列表 参数见 UDBTypeSet |No|

#### 数据模型


#### UDBTypeSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DBTypeId** | string | DB类型id，mysql/mongodb按版本细分各有一个id, 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBType
&Region=cn-bj2
&Zone=cn-bj2-04
&InstanceMode=Normal
&DiskType=hdd
&DBClusterType=mysql
&BackupZone=cn-bj2-03
&CompatibleWithDBTyp=tFbuDJNk
&DiskType=YQQrlDqy
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBTypeResponse",
  "DataSet": [
    {
      "DBTypeId": "mysql-5.1"
    },
    {
      "DBTypeId": "mysql-5.5"
    },
    {
      "DBTypeId": "percona-5.5"
    },
    {
      "DBTypeId": "mongodb-2.4"
    }
  ],
  "RetCode": 0
}
```





