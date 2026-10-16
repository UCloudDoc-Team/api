# 获取云游戏服务器列表 - DescribeUGameServer

## 简介

获取云游戏服务器列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGameServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUGameCities)获取 |**Yes**|
| **ServerIds.N** | string | 【数组】云游戏服务器的资源 ID，调用方式举例：ServerIds.0=希望获取信息的服务器 1，ServerIds.1=服务器 2。 如果不传入，则返回当前 城市 所有符合条件的云游戏服务器。 |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|

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
| **ServerId** | string | 云游戏服务器的唯一标识。 |**Yes**|
| **ServerName** | string | 云游戏服务器名称。 |**Yes**|
| **ServerModel** | [*ServerModelInstance*](#ServerModelInstance) | 云游戏服务器规格。 |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **ExpireTime** | int | 到期时间，格式为Unix时间戳。 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为：<br /> *Year，按年付费；<br />* Month，按月付费；<br />默认为月付 |**Yes**|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-jinan |**Yes**|
| **CityName** | string | 城市名称，eg:上海二、济南市 |**Yes**|
| **Bandwidth** | int | 带宽，单位M |No|
| **Remark** | string | 云游戏服务器备注。 |No|
| **AllocatedCount** | int | 配分游戏数量。 |No|
| **State** | string | 实例状态，枚举值： * 初始化: Initializing; * 云手机创建中: UPhoneCreating; * 运行中: Running; * 删除中: Deleting; * 创建失败: CreateFailed * 未知(空字符串，获取状态超时或出错)："" |No|
| **SchedulerState** | string | 锁定/非锁定状态 |No|
| **GpuUuids** | array[string] | 【数组】GPU设备Id |No|

#### ServerModelInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ServerModelName** | string | ServerModel名称 |No|
| **Cpu** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。 |No|
| **Memory** | int | 内存大小。单位：MB。 |No|
| **DiskSet** | array[[*DiskSet*](#DiskSet)] | 磁盘信息见 UPhoneDiskSet |No|
| **GpuType** | string | GPU类型 |No|
| **Gpu** | int | GPU个数 |No|
| **ServerModelState** | string | 表示该机型是否上线，用于前端判断是否开放给用户。枚举值：<br />>AVAILABLE，开放<br />>UNAVAILABLE, 不开放 |No|

#### DiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskType** | string | 磁盘类型。请参考磁盘类型。 |**Yes**|
| **IsBoot** | boolean | 是否是系统盘。枚举值：<br /><br />> True，是系统盘<br /><br />> False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Size** | int | 磁盘大小，单位: GB |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGameServer
&ProjectId=lwvZaFcZ
&CityId=zsBodJUk
&ServerIds.N=otNJROqP
&Offset=BkXxsBkK
&Limit=RiInCEen
```

### 响应示例
    
```json
{
  "Action": "DescribeUGameServerResponse",
  "Message": "nmYijAJG",
  "RetCode": 0,
  "Servers": [
    {
      "ChargeType": "NKpnJvfm",
      "CityId": "KQDXKAWB",
      "CityName": "MxWwgokb",
      "CreateTime": 7,
      "ExpireTime": 5,
      "GpuUuids": [
        "lVOXbdQA"
      ],
      "ModifyTime": 4,
      "Remark": "tVjpxUaq",
      "ServerId": "qqCUqvbv",
      "ServerModel": {},
      "ServerName": "cilVCIXj",
      "State": "lriebKOw",
      "UPhoneCount": 8
    }
  ],
  "TotalCount": 1
}
```





