# 获取云数据库状态-DescribeUDBInstanceState

获取UDB实例状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|State|string|DB状态标记 Init：初始化中；Fail：安装失败； Starting：启动中； Running ： 运行 ；Shutdown：关闭中； Shutoff ：已关闭； Delete：已删除； Upgrading：升级中； Promoting： 提升为独库进行中； Recovering： 恢复中； Recover fail：恢复失败。|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceState
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceStateResponse", 
    "State": "Running", 
    "RetCode": 0
}
```

