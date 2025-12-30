# 获取轻量应用云主机列表 - DescribeULHostInstance

## 简介

获取轻量应用云主机列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ULHostIds.N** | string | 【数组】轻量应用云主机ID。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ULHostInstanceSets** | array[[*ULHostInstanceSet*](#ULHostInstanceSet)] | 实例列表 |**Yes**|

#### 数据模型


#### ULHostInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。 |No|
| **ULHostId** | string | 实例Id。 |No|
| **Name** | string | 实例名称。默认套餐Id |No|
| **Tag** | string | 业务组。 |No|
| **Remark** | string | 备注。 |No|
| **ImageId** | string | 镜像Id。 |No|
| **ImageName** | string | 镜像名称。 |No|
| **Apps** | array[string] | 【数组】镜像包含的应用列表。 |No|
| **CPU** | int | CPU核数。 |No|
| **Memory** | int | 内存。单位：MB |No|
| **State** | string | 实例状态。枚举值：<br /><br /> >初始化: Initializing; <br /><br /> >启动中: Starting; <br /><br />> 运行中: Running; <br /><br />> 关机中: Stopping; <br /><br /> >关机: Stopped <br /><br /> >安装失败: Install Fail; <br /><br /> >重启中: Rebooting; <br /><br /> > 未知(空字符串，获取状态超时或出错)："" |No|
| **ChargeType** | string | 计费模式。枚举值：Month/Year |No|
| **IPSet** | array[[*UHostIPSet*](#UHostIPSet)] | IP信息 |No|
| **DiskSet** | array[[*ULHostDiskSet*](#ULHostDiskSet)] | 磁盘信息 |No|
| **EIPExclusiveUTPInfo** | [*ExclusiveUTPInfo*](#ExclusiveUTPInfo) | 流量包详情信息 |No|
| **AutoRenew** | string | 是否自动续费。枚举值：Yes/No |No|
| **IsExpire** | string | 是否过期。枚举值：Yes/No |No|
| **ExpireTime** | int | 过期时间。Unix时间戳 |No|
| **CreateTime** | int | 创建时间。Unix时间戳 |No|

#### UHostIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPMode** | string | IPv4/IPv6； |**Yes**|
| **Default** | string | 内网 Private 类型下，表示是否为默认网卡。true: 是默认网卡；其他值：不是。 |No|
| **Mac** | string | 内网 Private 类型下，当前网卡的Mac。 |No|
| **Weight** | int | 当前EIP的权重。权重最大的为当前的出口IP。 |No|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | 外网IP资源ID 。(内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb  (内网IP不显示带宽信息) |No|
| **VPCId** | string | IP地址对应的VPC ID。（华北（北京）不支持，字段返回为空） |No|
| **SubnetId** | string | IP地址对应的子网 ID。（华北（北京）不支持，字段返回为空） |No|
| **NetworkInterfaceId** | string | 弹性网卡为默认网卡时，返回对应的 ID 值 |No|

#### ULHostDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskId** | string | 磁盘Id |No|
| **DiskType** | string | 磁盘类型。如："CLOUD_RSSD"、"CLOUD_SSD" |No|
| **Type** | string | 磁盘类型。系统盘："Boot"；数据盘："Data" |No|
| **Size** | int | 磁盘大小。单位：GB |No|
| **IsBoot** | string | 是否为系统盘。是："True"；否："False" |No|
| **Drive** | string | 磁盘盘符。系统盘："vda" |No|

#### ExclusiveUTPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TotalSize** | int | 当前周期总流量 |No|
| **AvailableSize** | int | 当前周期剩余流量 |No|
| **UsedSize** | int | 当前周期已使用流量 |No|
| **ExcessSize** | int | 当前周期超出限额的流量 |No|
| **LastResetTime** | int | 上次重置时间 |No|
| **NextResetTime** | int | 下次重置时间 |No|
| **CreateTime** | int | 创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULHostInstance
&Region=cn-zj
&ProjectId=aoPMNqqb
&ULHostIds.N=YTKcvmGV
&Offset=7
&Limit=9
```

### 响应示例
    
```json
{
  "Action": "DescribeULHostInstanceResponse",
  "Message": "GmrflzlM",
  "RetCode": 0,
  "ULHostInstanceSets": [
    {
      "AutoRenew": "PyPNLqBH",
      "CPU": 1,
      "ChargeType": "hauEukUs",
      "CreateTime": 7,
      "DiskSet": [
        {
          "BackupType": "xHWomUhO",
          "DiskId": "MWvyrUwR",
          "DiskType": "IRrEynyl",
          "Drive": "RvmLbdKX",
          "Encrypted": "cNyCMNmT",
          "IsBoot": "tvSzSraj",
          "Name": "vsfpLPyr",
          "Size": 3,
          "Type": "UkyaHXBR"
        }
      ],
      "ExpireTime": 5,
      "IPSet": [
        {
          "Bandwidth": 2,
          "Default": "AnzSfoBi",
          "IP": "EOmBPJZd",
          "IPId": "vnrKbtka",
          "IPMode": "pWfqUmBy",
          "Mac": "DggLGvKF",
          "NetworkInterfaceId": "oTgcJktO",
          "SubnetId": "RfEGLEoc",
          "Type": "BVSGfRvP",
          "VPCId": "lrFLnZeF",
          "Weight": 9
        }
      ],
      "IsExpire": "dQxEsaLW",
      "Memory": 7,
      "Name": "jsqzqDEj",
      "Remark": "tJoNHAEH",
      "State": "CagCpoZQ",
      "Tag": "zQppWJxb",
      "ULHostId": "hcquybJV"
    }
  ]
}
```





