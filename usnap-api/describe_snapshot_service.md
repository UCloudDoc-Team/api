# 获取磁盘快照服务列表 - DescribeSnapshotService

## 简介

获取磁盘快照服务列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSnapshotService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 返回数据长度, 默认为20 |No|
| **VDiskId** | string | 磁盘ID (传入则获取当前盘快照服务, 不传则获取当前可用区快照服务列表)	 |No|
| **SnapshotId** | string | 快照ID (传入则获取当前快照对应盘的快照服务, 不传则获取当前可用区快照服务列表，磁盘ID和快照ID同时传入以磁盘ID为准) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*SnapshotServiceDataSet*](#SnapshotServiceDataSet)] | 快照服务列表 |No|
| **TotalCount** | int | 快照服务DataSet总数 |No|

#### 数据模型


#### SnapshotServiceDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区信息 |No|
| **CreateTime** | int | 创建时间 |**Yes**|
| **VDiskId** | string | 磁盘Id |**Yes**|
| **Status** | string | 状态:Available(可用),InAvailable(不可用),Expired(欠费) |**Yes**|
| **VDiskType** | string | "UDiskData" 云盘数据盘； ”UDiskBoot“ 云盘系统盘 |**Yes**|
| **VDiskStatus** | int | 磁盘是否可用，1表示可用，0表示不可用 |**Yes**|
| **VDiskSize** | int | 磁盘大小 （G） |**Yes**|
| **ServiceId** | string | 服务ID |No|
| **VDiskName** | string | 磁盘名 |No|
| **ExpiredTime** | int | 过期时间 |No|
| **ChargeType** | string | 计费类型 |No|
| **IsExpire** | string | 计费是否过期 |No|
| **AutoRenew** | string | 是否自动续费 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSnapshotService
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=CeigGZFc
&Offset=9
&Limit=4
&VDiskId=BEjwyiFd
&SnapshotId=JAQOCYXO
&SnapshotId=zSeLTmxM
```

### 响应示例
    
```json
{
  "Action": "DescribeSnapshotServiceResponse",
  "DataSet": [
    {
      "CreateTime": 5,
      "ServiceId": "PRTbzCzM",
      "Status": "vVArIRBK",
      "VDiskId": "gHjSEVdN"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





