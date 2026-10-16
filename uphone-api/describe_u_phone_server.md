# 获取云手机服务器列表 - DescribeUPhoneServer

## 简介

获取云手机服务器列表信息。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ServerIds.N** | string | 【数组】云手机服务器的资源 ID，调用方式举例：ServerIds.0=希望获取信息的服务器 1，ServerIds.1=服务器 2。 如果不传入，则返回当前 城市 所有符合条件的云手机服务器。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | ServerInstance总数 |**Yes**|
| **Servers** | array[[*ServerInstance*](#ServerInstance)] | 云手机服务器列表，每项参数可见数据模型 [ServerInstance](#ServerInstance) |**Yes**|

#### 数据模型


#### ServerInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ServerId** | string | 云手机服务器的唯一标识。 |**Yes**|
| **ServerName** | string | 云手机服务器名称。 |**Yes**|
| **ServerModel** | [*ServerModelInstance*](#ServerModelInstance) | 云服务器规格。 |**Yes**|
| **UPhoneModelName** | string | 云手机规格名称。 |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **ExpireTime** | int | 到期时间，格式为Unix时间戳。 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为：<br />  *Year，按年付费；<br />*  Month，按月付费；<br />默认为月付 |**Yes**|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-jinan |**Yes**|
| **CityName** | string | 城市名称，eg:上海二、济南市 |**Yes**|
| **Remark** | string | 云服务器备注。 |No|
| **UPhoneCount** | int | 云手机开数。 |No|
| **State** | string | 实例状态，枚举值： <br />* 初始化: Initializing; <br />* 云手机创建中: UPhoneCreating;<br />* 运行中: Running; <br />* 删除中: Deleting; <br />* 创建失败: CreateFailed <br />* 未知(空字符串，获取状态超时或出错)："" |No|
| **IpSet** | array[[*IpSet*](#IpSet)] | 服务器IP信息 |No|

#### ServerModelInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ServerModelName** | string | ServerModel名称	 |No|
| **CPU** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。 |No|
| **Memory** | int | 内存大小。单位：MB。 |No|
| **DiskSet** | array[[*ServerDiskSet*](#ServerDiskSet)] | 磁盘信息见 UPhoneDiskSet	 |No|
| **GPUType** | string | GPU类型	 |No|
| **GPU** | int | GPU个数	 |No|
| **UPhoneSpecs** | array[[*UPhoneSpec*](#UPhoneSpec)] | 【数组】手机说明，包含该服务器规格所能创建的手机规格名及对应手机开数。每项参数可见数据模型 [UPhoneSpec](#UPhoneSpec)	 |No|
| **ServerModelState** | string | 表示该机型是否上线，用于前端判断是否开放给用户。枚举值：<br />>AVAILABLE，开放<br />>UNAVAILABLE, 不开放 |No|

#### IpSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | IP地址 |No|
| **IpMode** | string | ipv4或者ipv6 |No|
| **IpType** | string | 共有或私有 |No|
| **Isp** | string | 运营商 |No|

#### ServerDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskType** | string | 磁盘类型。请参考磁盘类型。 |**Yes**|
| **IsBoot** | boolean | 是否是系统盘。枚举值：<br /><br />> True，是系统盘<br /><br />> False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Size** | int | 磁盘大小，单位: GB |**Yes**|

#### UPhoneSpec

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPhoneModelName** | string | 手机规格名 |No|
| **UPhoneCount** | int | 手机开数，即该服务器规格能生成对应手机规格的云手机个数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneServer
&ProjectId=VAMEnKcG
&CityId=tAkKItkw
&ServerIds.N=xgUAbtfV
&Offset=1
&Limit=6
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneServerResponse",
  "Message": "LoGJkbOY",
  "RetCode": 0,
  "Servers": [
    {
      "ChargeType": "RopjIgxf",
      "CityId": "CWDBbKBL",
      "CityName": "aFTpZTwl",
      "CreateTime": 5,
      "ExpireTime": 3,
      "GPUIds": [
        "HfIyIjMg"
      ],
      "ModifyTime": 2,
      "Remark": "JHXviQLY",
      "ServerId": "PGGblQyq",
      "ServerModel": {},
      "ServerName": "YNfpXzFt",
      "State": "ioJVrohw",
      "UPhoneCount": 3,
      "UPhoneModelName": "XfYOCdnp"
    }
  ],
  "TotalCount": 1
}
```





