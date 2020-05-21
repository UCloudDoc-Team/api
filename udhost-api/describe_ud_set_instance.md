# 列出资源池下的UDhost实例 - DescribeUDSetInstance

## 简介

列出资源池下的UDhost实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDSetInstance)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDSetInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **HostIds.N** | string | 资源池的短ID, 如果为空, 则返回当前Region所有符合条件的UHost实例，否则返回指定资源池上的所有UHost实例 |No|
| **UHostIds.N** | string | 专区主机的短ID, 如果为空, 则返回指定资源池的UHost实例，否则返回指定主机的实例信息 |No|
| **Tag** | string | 要查询的业务组名称 |No|
| **Offset** | int | 主机数据偏移量, 默认为0 |No|
| **Limit** | int | 返回主机数据长度, 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的总数 |No|
| **UHostSet** | array[[*UDSetInstanceSet*](#UDSetInstanceSet)] | 满足条件的私有专区主机列表 |No|

#### 数据模型


#### UDSetInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **UHostId** | string | UHost实例ID |No|
| **HostId** | string | 资源池短ID |No|
| **UHostType** | string | Normal：标准机型，SSD：SSD机型 |No|
| **OsType** | string | 操作系统类型: Liunx, Windows |No|
| **OsName** | string | 操作系统名称 |No|
| **ImageId** | string | 镜像Id |No|
| **BasicImageId** | string | 基础镜像Id |No|
| **BasicImageName** | string | 基础镜像名称 |No|
| **Tag** | string | 业务组名称 |No|
| **Remark** | string | 备注 |No|
| **Name** | string | 实例名称 |No|
| **State** | string | 实例状态, 初始化:Initializing, 启动中:Starting, 运行中:Running, 关机中:Stopping,关机:Stopped, 安装失败:Install Fail, 重启中:Rebooting   重置密码中   迁移中 |No|
| **ExpireTime** | int | 到期时间 |No|
| **CPU** | int | 虚拟CPU核数, 单位:个 |No|
| **Memory** | int | 内存大小, 单位:MB |No|
| **DiskSet** | array[[*UHostDiskSet*](#UHostDiskSet)] | 磁盘信息 |No|
| **NetCapability** | string | 正常：Normal；网络增强：Enhance |No|
| **IPSet** | array[[*UHostIPSet*](#UHostIPSet)] | IP信息 |No|
| **SubnetType** | string | 是否私有网络，Default，Private |No|
| **NetworkState** | string | Connected，NotConnected |No|
| **TimemachineFeature** | string | 是否开启数据方舟。Yes: 开启；No：未开启。 |No|
| **BootDiskState** | string | 系统盘状态。在Initializing时主机不能创建镜像。 |No|

#### UHostDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 磁盘类型。系统盘: Boot，数据盘: Data,网络盘：Udisk |No|
| **DiskId** | string | 磁盘ID |No|
| **Name** | int | UDisk名字（仅当磁盘是UDisk时返回） |No|
| **Drive** | int | 磁盘盘符 |No|
| **Size** | int | 磁盘大小，单位: GB |No|

#### UHostIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 国际: Internation，BGP: Bgp，内网: Private |No|
| **IPId** | string | IP资源ID (内网IP无对应的资源ID) |No|
| **IP** | string | IP地址 |No|
| **Bandwidth** | int | IP对应的带宽, 单位: Mb (内网IP不显示带宽信息) |No|
| **Default** | string | 是否默认的弹性网卡的信息。true: 是默认弹性网卡；其他值：不是。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn?Action=DescribeUDSetInstance
&Region=mBqVzITv
&HostIds.n=XhwutBWo
&UHostIds.n=dPplcWeS
&Tag=yoOOTstO
&Offset=9
&Limit=FMICfjGc
&ProjectId=nihbmJrX
```

### 响应示例
    
```json
{
  "Action": "DescribeUDSetInstanceResponse",
  "RetCode": 0,
  "TotalCount": 1,
  "UHostSet": [
    {
      "BasicImageId": "uimage-qegj3w",
      "BasicImageName": "CentOS 6.5 64位",
      "BootDiskState": "Initializing",
      "CPU": 2,
      "CreateTime": 1543333491,
      "DiskSet": [
        {
          "DiskId": "7fe9a7ce-8414-400a-80c7-a5325419b0fb",
          "Drive": "vda",
          "Size": 20,
          "Type": "Boot"
        },
        {
          "DiskId": "9f23a13e-c14c-43f9-a530-8d2c1993a186",
          "Drive": "vdb",
          "Size": 20,
          "Type": "Data"
        }
      ],
      "HostId": "udset-xxx",
      "IPSet": [
        {
          "IP": "10.9.159.36",
          "SubnetId": "subnet-xxx",
          "Type": "Private",
          "VPCId": "uvnet-xxx"
        }
      ],
      "ImageId": "7fe9a7ce-8414-400a-80c7-a5325419b0fb",
      "Memory": 4096,
      "Name": "test",
      "NetCapability": "Normal",
      "NetworkState": "Connected",
      "OsName": "CentOS 6.5 64位",
      "OsType": "Linux",
      "Remark": "",
      "State": "Running",
      "SubnetType": "Default",
      "Tag": "Default",
      "TimemachineFeature": "no",
      "TotalDiskSpace": 20,
      "UHostId": "udhost-xxx",
      "UHostType": "Normal",
      "Zone": "cn-bj2-02"
    }
  ]
}
```





