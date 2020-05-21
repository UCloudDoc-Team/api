# 查询主备Redis - DescribeURedisGroup

## 简介

查询主备Redis






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeURedisGroup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURedisGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **GroupId** | string | 组的ID,如果指定则获取描述，否则为列表操 作,需指定Offset/Limit |No|
| **Offset** | int | 分页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 分页显示的条目数, 默认值为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 组的总的节点个数 |No|
| **DataSet** | array[[*URedisGroupSet*](#URedisGroupSet)] | 组列表 参见 URedisGroupSet |No|

#### 数据模型


#### URedisGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 实例所在可用区，或者master redis所在可用区，参见 [可用区列表](api/summary/regionlist) |No|
| **VPCId** | string | VPCId |**Yes**|
| **RewriteTime** | int | 返回运维时间 0 //0点 1 //1点 以此类推 |**Yes**|
| **Role** | string | 实例类型 |**Yes**|
| **GroupId** | string | 组ID |No|
| **Name** | string | 组名称 |No|
| **Type** | string | 空间类型:single(无热备),double(热备) |No|
| **SubnetId** | string | 子网 |No|
| **Protocol** | string | 协议 |No|
| **MemorySize** | int | 容量单位GB |No|
| **GroupName** | string | 组名称 |No|
| **ConfigId** | string | 节点的配置ID |No|
| **VirtualIP** | string | 节点的虚拟IP地址 |No|
| **Port** | int | 节点分配的服务端口 |No|
| **Size** | int | 容量单位GB |No|
| **UsedSize** | int | 使用量单位MB |No|
| **AutoBackup** | string | 是否需要自动备份,enable,disable |No|
| **BackupTime** | int | 组自动备份开始时间,单位小时计,范围[0-23] |No|
| **HighAvailability** | string | 是否开启高可用,enable,disable |No|
| **Version** | string | Redis版本信息 |No|
| **ExpireTime** | int | 过期时间 (UNIX时间戳) |No|
| **ChargeType** | string | 计费类型:Year,Month,Dynamic 默认Dynamic |No|
| **State** | string | 状态标记 Creating // 初始化中 CreateFail // 创建失败 Deleting // 删除中 DeleteFail // 删除失败 Running // 运行 Resizing // 容量调整中 ResizeFail // 容量调整失败 Configing // 配置中 ConfigFail // 配置失败 |No|
| **CreateTime** | int | 创建时间 (UNIX时间戳) |No|
| **ModifyTime** | int | 修改时间 (UNIX时间戳) |No|
| **Tag** | string | 业务组名称 |No|
| **SlaveZone** | string | 跨机房URedis，slave redis所在可用区，参见 [可用区列表](api/summary/regionlist) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURedisGroup
&Region=cn-bj2
&Zone=SZQDzLQZ
```

### 响应示例
    
```json
{
  "Action": "DescribeURedisGroupResponse",
  "DataSet": [
    {
      "AutoBackup": "disable",
      "BackupTime": 3,
      "ChargeType": "Month",
      "ConfigId": "03fXXXXca9-b64d-4XXd-abc7-c6b9XXXXX801",
      "CreateTime": 1529912330,
      "ExpireTime": 1530374400,
      "GroupId": "uredis-gXXXXXbz",
      "GroupName": "zbredia_XXXXX_modify",
      "HighAvailability": "enable",
      "MemorySize": 4,
      "ModifyTime": 1529912337,
      "Name": "zbreXXia_XXXXX_modify",
      "Port": 6379,
      "Protocol": "redis",
      "Size": 4,
      "SlaveZone": "",
      "State": "Running",
      "SubnetId": "subnet-iXXXXhz",
      "Tag": "Default",
      "Type": "double",
      "UsedSize": 61,
      "VPCId": "uvnet-oXXXX4j",
      "Version": "3.0",
      "VirtualIP": "XX.X9.XX.1XX",
      "Zone": "cn-bj2-04"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





