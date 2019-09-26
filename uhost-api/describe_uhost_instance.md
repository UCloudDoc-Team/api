# 获取主机信息-DescribeUHostInstance
# 获取主机或主机列表信息，并可根据数据中心，主机ID等参数进行过滤。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostIds.N|string|【数组】UHost主机的资源ID，例如UHostIds.0代表希望获取信息 的主机1，UHostIds.1代表主机2。 如果不传入，则返回当前Region 所有符合条件的UHost实例。|No|
|Tag|string|要查询的业务组名称|No|
|LifeCycle|int|1：普通云主机；2：抢占型云主机；如不传此参数，默认全部获取|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|
|IsolationGroup|string|硬件隔离组id。通过硬件隔离组筛选主机。|No|
|VPCId|string|vpc id。通过VPC筛选主机。北京一地域无效。|No|
|SubnetId|string|子网id。通过子网筛选主机。北京一地域无效。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|UHostInstance总数|No|
|UHostSet|array|云主机实例列表，每项参数可见下面 UHostInstanceSet|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&Offset=0
&Limit=20
&UHostIds.0=uhost-xxx
&IsolationGroup=lvbanUiO
&VPCId=SNCWNQEL
&SubnetId=nWauQBws```

# Response Example
```
{"Action": "DescribeUHostInstanceResponse", "TotalCount": 1, "RetCode": 0, "UHostSet": [{"Zone": "cn-bj2-04", "OsName": "CentOS 6.5 64\u4f4d", "HostType": "N2", "State": "Running", "Memory": 8192, "NetCapability": "Normal", "BootDiskState": "Normal", "CPU": 4, "BasicImageName": "1", "IPSet": [{"SubnetId": "subnet-xxxx", "IP": "10.19.xxx.xxx", "Mac": "xxx", "VPCId": "uvnet-xxx", "Type": "Private"}], "NetCapFeature": true, "ImageId": "xxx", "AutoRenew": "Yes", "TotalDiskSpace": 20, "OsType": "Linux", "DiskSet": [{"Encrypted": "No", "Type": "Boot", "Drive": "vda", "DiskId": "xxx", "Size": 20}, {"Encrypted": "No", "Type": "Data", "Drive": "vdb", "DiskId": "xxx", "Size": 20}], "SubnetType": "Default", "Remark": "", "Name": "UHost", "UHostId": "uhost-xxx", "GPU": 0, "LifeCycle": "Normal", "StorageType": "LocalDisk", "HotplugFeature": false, "UHostType": "Normal", "BasicImageId": "uimage-xxx", "ExpireTime": 1532483542, "Tag": "Default", "NetworkState": "Connected", "ChargeType": "Month", "CreateTime": 1529891542, "TimemachineFeature": "no"}]}```

