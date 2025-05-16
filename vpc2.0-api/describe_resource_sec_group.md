# 查询资源绑定的安全组信息 - DescribeResourceSecGroup

## 简介

查询资源绑定的安全组信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeResourceSecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeResourceSecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceType** | string | 资源类型，如 uhost, uni |No|
| **Offset** | int | 分页查询时的偏移量。传入了 ResourceId 则不分页。 |No|
| **Limit** | int | 分页查询时的最大返回资源数量。 |No|
| **VPCId** | string | VPC ID。非必须，分页使用（分页时，也可不传）；ResourceId 非空时，忽略 |No|
| **ResourceId** | string | 资源 ID 数组，如果指定则不分页；否则分页获取该账号下的指定类型的资源。不支持 .n 格式。Type 为 string 数组。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 资源总数量。传入 ResourceId 时，为传入资源中的有效资源数量。 |**Yes**|
| **DataSet** | array[[*ResourceSecgroupInfoEx*](#ResourceSecgroupInfoEx)] | 资源绑定的安全组信息 |**Yes**|

#### 数据模型


#### ResourceSecgroupInfoEx

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源 ID |**Yes**|
| **ResourceName** | string | 资源名称 |**Yes**|
| **Count** | int | 该资源绑定的安全组数量 |**Yes**|
| **SecGroupInfo** | array[[*BindingSecGroupInfo*](#BindingSecGroupInfo)] | 绑定安全组信息 |**Yes**|
| **PermitAssociate** | boolean | 表示是否允许绑定安全组 |**Yes**|
| **ExInfo** | [*ResourceExInfo*](#ResourceExInfo) | 资源额外信息 |No|

#### BindingSecGroupInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecGroupId** | string | 安全组 ID |No|
| **Name** | string | 安全组名称 |No|
| **VPCId** | string | 安全组所属 VPC |No|
| **Priority** | int | 该资源与该安全组绑定的优先级 |No|

#### ResourceExInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SuperResourceId** | string | 父级资源ID |**Yes**|
| **ResourceName** | string | 资源名称 |No|
| **IP** | array[string] | 主机内网IP |No|
| **EIP** | array[string] | 主机外网IP |No|
| **Uni** | array[[*ResourceSecgroupInfo*](#ResourceSecgroupInfo)] | 弹性网卡信息 |No|
| **SuperResourceName** | string | 父级资源名称 |No|

#### ResourceSecgroupInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **Count** | int | 资源绑定安全组数量 |**Yes**|
| **SecGroupInfo** | array[[*SecGroupSimpleInfo*](#SecGroupSimpleInfo)] | 详见SecGroupSimpleInfo |No|

#### SecGroupSimpleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecGroupId** | string | 安全组资源ID |No|
| **Name** | string | 安全组名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeResourceSecGroup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=bKOyoPxS
&ResourceType=ECVHqgZo
&ResourceId.n=YziDaDxa
&Offset=4
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "DescribeResourceSecGroupResponse",
  "DataSet": [
    {
      "Count": 6,
      "ResourceId": "ljSwPBgv",
      "SecGroupInfo": [
        {
          "Name": "ohoFGMfk",
          "SecGroupId": "aVrzsMDI"
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 4
}
```





