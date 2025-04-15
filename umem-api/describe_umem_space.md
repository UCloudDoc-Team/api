# 查询空间 - DescribeUMemSpace

## 简介

获取UMem内存空间列表（已废弃，建议是使用DescribeUMem接口）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemSpace)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemSpace`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 返回数据长度, 默认为20 |No|
| **SpaceId** | string | 内存空间ID (无ID，则获取所有) |No|
| **Protocol** | string | 协议类型: memcache, redis |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UMemSpaceSet*](#UMemSpaceSet)] | JSON 格式的UMem内存空间实例列表, 详细参见 UMemSpaceSet |No|
| **TotalCount** | int | 根据过滤条件得到的总数 |No|

#### 数据模型


#### UMemSpaceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，参见[可用区列表](api/summary/regionlist) |No|
| **Tag** | string | 实例tag |**Yes**|
| **RewriteTime** | int | 运维时间<br />0   //0点<br />1   //1点<br />依次类推 |**Yes**|
| **SpaceId** | string | 内存空间ID |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC ID |No|
| **Name** | string | 内存空间名称 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **Type** | string | 空间类型:single(无热备),double(热备) |No|
| **Protocol** | string | 协议类型: memcache, redis |No|
| **Size** | int | 容量单位GB |No|
| **UsedSize** | int | 使用量单位MB |No|
| **State** | string | Starting:创建中 Running:运行中 Fail:失败 |No|
| **ChargeType** | string | Year, Month, Dynamic, Trial |No|
| **Address** | array[[*UMemSpaceAddressSet*](#UMemSpaceAddressSet)] | IP端口信息请参见 UMemSpaceAddressSet |No|
| **SupportAofRollback** | boolean | 实例是否支持回档 |No|
| **AofRollbackEnable** | boolean | 实例是否开启了回档 |No|

#### UMemSpaceAddressSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | UMem实例访问IP |No|
| **Port** | int | UMem实例访问Port |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemSpace
&Region=cn-bj2

&Protocol=dSWWMtLZ
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemSpaceResponse",
  "DataSet": [
    {
      "Address": [
        {
          "IP": "XX.19X.1XX.4XX",
          "Port": 11211
        }
      ],
      "ChargeType": "Month",
      "CreateTime": 1529894002,
      "ExpireTime": 1530374400,
      "Name": "fbs_XXXX",
      "Protocol": "memcache",
      "Size": 8,
      "SpaceId": "umem-m3XXXXXX3",
      "State": "Running",
      "SubnetId": "subnet-iiXXXXz",
      "Tag": "Default",
      "Type": "double",
      "UsedSize": 0,
      "VPCId": "uvnet-XXXXXX4j",
      "Zone": "cn-bj2-04"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





