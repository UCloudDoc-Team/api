# 查询快照一致性组详情信息 - DescribeUSnapGroup

## 简介

查询快照一致性组详情信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUSnapGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **GroupId** | string | 一致性组快照ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SnapshotList** | array[[*SnapInfo*](#SnapInfo)] | 快照列表信息 |**Yes**|

#### 数据模型


#### SnapInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SnapshotId** | string | 快照ID |**Yes**|
| **VDiskType** | string | 磁盘类型：系统盘 Boot 数据盘 Data |**Yes**|
| **Size** | int | 快照大小GB |**Yes**|
| **VdiskId** | string | 磁盘ID |**Yes**|
| **Status** | string | 快照状态: 制作中Creating 完成 Normal 失败Failed |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUSnapGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=UZJdgtUQ
&GroupId=EsjhSUcU
```

### 响应示例
    
```json
{
  "Action": "DescribeUSnapGroupResponse",
  "GroupList": [
    {
      "CreateTime": 5,
      "DataCount": 9,
      "GroupId": "rHOAEhzu",
      "Name": "UiBCBHAe",
      "Status": "fmHecChx",
      "SysCount": 1
    }
  ],
  "RetCode": 0
}
```





