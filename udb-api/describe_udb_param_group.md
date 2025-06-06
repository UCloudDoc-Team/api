# 获取参数信息 - DescribeUDBParamGroup

## 简介

获取参数组详细参数信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBParamGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBParamGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 分页显示的起始偏移，列表操作则指定 |**Yes**|
| **Limit** | int | 分页显示的条目数，列表操作则指定 |**Yes**|
| **GroupId** | int | 参数组id，如果指定则获取描述，否则是列表操作，需要 指定Offset/Limit |No|
| **IsInUDBC** | boolean | 是否选取专区中配置 |No|
| **RegionFlag** | boolean | 当请求没有填写Zone时，如果指定为true，表示只拉取跨可用区的相关配置文件，否则，拉取所有机房的配置文件（包括每个单可用区和跨可用区） |No|
| **ClassType** | string | 如果未指定GroupId，则可选是否选取特定DB类型的配置(sql, nosql, postgresql, sqlserver) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBParamGroupSet*](#UDBParamGroupSet)] | 参数组列表 参照UDBParamGroupSet |No|
| **TotalCount** | int | 参数组总数，列表操作时才会有该参数 |No|

#### 数据模型


#### UDBParamGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupType** | int | 参数组类型：1：稳定版参数组，2:高性能版参数组。默认是稳定版参数组 |No|
| **GroupId** | int | 参数组id |No|
| **GroupName** | string | 参数组名称 |No|
| **DBTypeId** | string | DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6 7：percona-5.6 |No|
| **Description** | string | 参数组描述 |No|
| **Modifiable** | boolean | 参数组是否可修改 |No|
| **ParamMember** | array[[*UDBParamMemberSet*](#UDBParamMemberSet)] | 参数的键值对表 UDBParamMemberSet |No|

#### UDBParamMemberSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 参数名称 |No|
| **Value** | string | 参数值 |No|
| **ValueType** | int | 参数值应用类型，取值范围为{0,10,20,30},各值 代表意义为 0-unknown、10-int、20-string、 30-bool |No|
| **AllowedVal** | string | 允许的值(根据参数类型，用分隔符表示) |No|
| **ApplyType** | int | 参数值应用类型,取值范围为{0,10,20}，各值代表 意义为0-unknown、10-static、20-dynamic |No|
| **Modifiable** | boolean | 是否可更改，默认为false |No|
| **FormatType** | int | 允许值的格式类型，取值范围为{0,10,20}，意义分 别为PVFT_UNKOWN=0,PVFT_RANGE=10, PVFT_ENUM=20 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBParamGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&Offset=0
&Limit=3                        
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBParamGroupResponse",
  "DataSet": [
    {
      "DBTypeId": "postgresql-9.6",
      "Description": "postgresql-9.6默认配置",
      "GroupId": 1859,
      "GroupName": "postgresql-9.6默认配置",
      "Modifiable": false,
      "ParamGroupTypeName": "Undefined",
      "RegionFlag": false,
      "Zone": "cn-bj2-02"
    },
    {
      "DBTypeId": "mysql-5.1",
      "Description": "mysql5.1默认配置",
      "GroupId": 2,
      "GroupName": "mysql5.1默认配置",
      "Modifiable": false,
      "ParamGroupTypeName": "Undefined",
      "RegionFlag": false,
      "Zone": "cn-bj2-02"
    },
    {
      "DBTypeId": "mysql-5.5",
      "Description": "mysql5.5默认配置",
      "GroupId": 1,
      "GroupName": "mysql5.5默认配置",
      "Modifiable": false,
      "ParamGroupTypeName": "Undefined",
      "RegionFlag": false,
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





