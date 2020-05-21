# 获取快照列表 - DescribeUDiskSnapshot

## 简介

获取UDisk快照






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDiskSnapshot)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDiskSnapshot`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 返回数据长度, 默认为20 |No|
| **UDiskId** | string | UDiskId,返回该盘所做快照.(必须同时传Zone) |No|
| **SnapshotId** | string | 快照id，SnapshotId , UDiskId 同时传SnapshotId优先 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDiskSnapshotSet*](#UDiskSnapshotSet)] | JSON 格式的Snapshot列表, 详细参见 UDiskSnapshotSet |No|
| **TotalCount** | int | 根据过滤条件得到的总数 |No|

#### 数据模型


#### UDiskSnapshotSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SnapshotId** | string | 快照Id |**Yes**|
| **Name** | string | 快照名称 |**Yes**|
| **UDiskId** | string | 快照的源UDisk的Id |**Yes**|
| **UDiskName** | string | 快照的源UDisk的Name |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Size** | int | 容量单位GB |**Yes**|
| **Status** | string | 快照状态，Normal:正常,Failed:失败,Creating:制作中 |**Yes**|
| **DiskType** | int | 磁盘类型，0:数据盘，1:系统盘 |**Yes**|
| **ExpiredTime** | int | 过期时间 |No|
| **Comment** | string | 快照描述 |No|
| **IsUDiskAvailable** | boolean | 对应磁盘是否处于可用状态 |No|
| **Version** | string | 快照版本 |No|
| **UHostId** | string | 对应磁盘制作快照时所挂载的主机 |No|
| **UKmsMode** | string | 是否是加密盘快照，是:"Yes", 否:"No" |No|
| **CmkId** | string | 该快照的cmk id |No|
| **DataKey** | string | 该快照的密文密钥 |No|
| **CmkIdStatus** | string | 该快照cmk的状态, Enabled(正常)，Disabled(失效)，Deleted(删除)，NoCmkId(非加密盘) |No|
| **CmkIdAlias** | string | cmk id 别名 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDiskSnapshot
&Region=cn-bj2
&SnapshotId=bsSnap-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeUDiskSnapshotResponse",
  "DataSet": [
    {
      "ChargeType": "Year",
      "Comment": "test",
      "CreateTime": 1402039500,
      "DiskType": 0,
      "ExpiredTime": 1402039500,
      "IsUDiskAvailable": true,
      "Name": "test",
      "Size": "100",
      "SnapshotId": "bsSnap-xxx",
      "Status": "Normal",
      "UDiskId": "bs-xxx",
      "UDiskName": "apidoctest",
      "UHostId": "uhost-xxx",
      "Version": "1.0"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





