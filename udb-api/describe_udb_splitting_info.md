# 描述读写分离功能 - DescribeUDBSplittingInfo

## 简介

描述读写分离功能的详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBSplittingInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBSplittingInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **MasterDBId** | string | DB实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Region** | string | 地域 |No|
| **Zone** | string | 可用区 |No|
| **MasterDBId** | string | DB实例ID |No|
| **RWIP** | string | 读写分离IP |No|
| **DelayThreshold** | int | 时间阈值 |No|
| **Port** | int | 端口号 |No|
| **ReadModel** | string | 读写分离策略 |No|
| **DBTypeId** | string | 数据库版本 |No|
| **RWState** | string | 读写分离状态 |No|
| **DataSet** | array[[*UDBRWSplittingSet*](#UDBRWSplittingSet)] | 读写分离从库信息 |No|
| **MainZone** | string | 可用区。跨机房读写分离的主可用区 |No|
| **BackupZone** | string | 可用区。跨机房读写分离的备可用区 |No|

#### 数据模型


#### UDBRWSplittingSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DBId** | string | DB实例ID |No|
| **Role** | string | 主库/从库 |No|
| **VirtualIP** | string | DBIP |No|
| **ReadWeight** | int | 读写分离比重 |No|
| **State** | string | DB状态 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBSplittingInfo
&Region=cn-zj
&Zone=cn-zj-01
&MasterDBId=NzgZOTgz
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBSplittingInfoResponse",
  "DBTypeId": "HZxiDykq",
  "DataSet": [
    {
      "DBId": "BpCreBes",
      "ReadWeight": 50,
      "Role": "master",
      "State": "iGyPHLGk",
      "VirtualIP": "FmcvWPOS"
    },
    {
      "DBId": "jBgxHUVS",
      "ReadWeight": 50,
      "Role": "master",
      "State": "aVUODePQ",
      "VirtualIP": "oisTbHGm"
    },
    {
      "DBId": "HBCtruVq",
      "ReadWeight": 50,
      "Role": "master",
      "State": "XPYHDmkt",
      "VirtualIP": "yfTsRDrt"
    },
    {
      "DBId": "BUXZmWJM",
      "ReadWeight": 50,
      "Role": "master",
      "State": "KkfYLRyo",
      "VirtualIP": "AwEZlxqz"
    }
  ],
  "DelayThreshold": 50,
  "MasterDBId": "fplVHdTl",
  "Port": 2,
  "RWIP": "LsGqmDqU",
  "RWState": "zBvozXGk",
  "ReadModel": "vFwGkIve",
  "Region": "cn-zj",
  "RetCode": 0,
  "Zone": "cn-zj-01"
}
```





