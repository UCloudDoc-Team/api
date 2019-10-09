

# 创建云主机(旧)-CreateUHostInstance

创建指定数量的UHost实例。该API将长期维护，但此API将不会提供SSD云盘支持等最新功能，建议您改用[新版创建云主机API](api/uhost-api/create_uhost_instance)。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|HostType|string|云主机系列。枚举值：<br> > N1，系列1<br> > N2，系列2<br> 建议您不要调用此字段，而通过参考[云主机机型说明](api/uhost-api/uhost_type)调用UHostType直接选择具体机型。|No|
|UHostType|string| 云主机机型。参考[云主机机型说明](api/uhost-api/uhost_type)。<br> 此外，还有这些枚举值支持传递（但不建议您使用）： <br> > Normal：普通型，根据HostType判断是N1还是N2 <br> > SATA\_SSD：高IO型，根据HostType判断是I1还是I2 <br> > BigData：大数据型，仅支持系列1 <br> > GPU：GPU机型，根据HostType判断是G1还是G2 |No|
|CPU|int|虚拟CPU核数。可选参数：1-32（可选范围与UHostType相关）。默认值: 4|No|
|Memory|int|内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围与UHostType相关）。默认值：8192|No|
|GPU|int|GPU卡核心数。仅GPU机型支持此字段（可选范围与UHostType相关）。|No|
|StorageType|string|磁盘类型，同时设定系统盘和数据盘的磁盘类型。枚举值为：<br> > LocalDisk，本地磁盘（机型为N1,N2,N3,D1时，此值代表创建普通本地盘；机型为G1,G2,G3,C1时，此值代表SSD本地盘）; <br>> UDisk，普通云盘；<br> 默认值：LocalDisk。仅北京二B/C/D/上海二A/B/广州可用区支持云硬盘方式的主机存储方式。无法通过此字段设置SSD云盘，若您希望更丰富的调用，建议您改用[新版创建云主机API](api/uhost-api/create_uhost_instance)|No|
|DiskSpace|int|数据盘大小。请参考[磁盘类型](api/uhost-api/disk_type)|No|
|TimemachineFeature|string|是否开启方舟特性。Yes为开启方舟，No为关闭方舟。仅普通本地盘情况下此处可以传Yes。默认为No。|No|
|NetCapability|string|网络增强。枚举值：<br> > Normal，不开启 <br> > Super，开启 <br> 默认值未为Normal。|No|
|VPCId|string|VPC ID。默认为当前地域的默认VPC。 |No|
|SubnetId|string|子网 ID。默认为当前地域的默认子网。 |No|
|PrivateIp.N|string|【数组】创建云主机时指定内网IP。若不传值，则随机分配当前子网下的IP。调用方式举例：PrivateIp.0=x.x.x.x。当前只支持一个内网IP。|No|
|SecurityGroupId|string|防火墙Id，默认为Web推荐防火墙。如何查询SecurityGroupId请参见[DescribeSecurityGroup](../unet-api/describe_security_group.html)|No|
|ImageId|string|镜像ID。请通过 [DescribeImage](describe_image.html)获取。|**Yes**|
|Password|string|UHost密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码。|**Yes**|
|Name|string|UHost实例名称。默认：UHost。请遵照[字段规范](api/uhost-api/specification)设定实例名称。|No|
|Tag|string|业务组。默认：Default（Default即为未分组）。请遵照[字段规范](api/uhost-api/specification)设定业务组。|No|
|ChargeType|string|计费模式。枚举值为： <br> > Year，按年付费； <br> > Month，按月付费；<br> > Dynamic，按小时付费 <br> 默认为月付。|No|
|Quantity|int|购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。月付时，此参数传0，代表了购买至月末。|No|
|CouponId|string|代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看。|No|

```
须按照控制台标准机型配置创建主机，详情请参考控制台。密码需要通过base64进行编码，
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|操作返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostIds|array|UHost实例Id集合|No|
|IPs|array|IP信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ImageId=uimage-xxxx
&Password=xxx
&LoginMode=Password
```
#Response Example
```
{
    "RetCode": 0,
    "Action": "CreateUHostInstanceResponse",
    "UHostIds": [
        "uhost-xxx"
    ],
    "IPs": [
        "10.19.xx.xxx"
    ]
}
```
