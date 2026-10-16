# 查询快照一致性组 - DescribeUSnapGroupList

## 简介

查询快照一致性组









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUSnapGroupList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **GroupId** | string | 一致性组快照ID,不填默认拉全量列表 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupList** | array[[*SnapGroupInfo*](#SnapGroupInfo)] | 一致性组快照列表信息 |**Yes**|
| **TotalCount** | int | 一致性组数量 |No|

#### 数据模型


#### SnapGroupInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 一致性组快照名 |**Yes**|
| **GroupId** | string | 一致性组快照ID |**Yes**|
| **Status** | string | 状态：创建中Creating  完成Normal  失败Failed |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **SysCount** | int | 系统盘快照数量 |**Yes**|
| **DataCount** | int | 数据盘快照数量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUSnapGroupList
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=qsjqWONX
&GroupId=AkcUQxwG
```

### 响应示例
    
```json
{
  "Action": "DescribeUSnapGroupListResponse",
  "GroupList": [
    {
      "CreateTime": 4,
      "DataCount": 7,
      "GroupId": "ctZqDsMV",
      "Name": "XfVkjlHH",
      "Status": "lJqbmSCf",
      "SysCount": 3
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





