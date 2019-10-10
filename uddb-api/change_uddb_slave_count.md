# 改变分布式数据库数据节点的只读实例个数-ChangeUDDBSlaveCount

改变分布式数据库数据节点的只读实例个数
每一个UDDB的数据节点负责处理所有的写入请求。与此同时，每一个数据节点可以配置若干个该节点的只读实例。当主节点的数据写入完毕后，只读实例把这次的写入操作进行更新，从而和数据节点保持一致。
只读实例可以使得数据由多份复制，在数据节点和只读实例之间，可以做请求的读写分离, 也就是说, 主节点写入数据之后, 数据的读操作可以由数据只读实例进行分担, 这样减少主节点的压力, 增加性能
当改变了数据节点的只读实例个数之后，对于现有的和以后的每一个数据节点都采用这个配置。如果UDDB实例有现有的数据节点, 那么它会根据新配置的参数，自动创建或删除数据节点的只读实例
如下状态的UDDB实例可以进行这个操作:
Running: 系统正常运行中
当请求返回成功之后，UDDB实例的状态变成"ChangingSlaveCount"; 如果返回失败, UDDB实例状态保持不变 当UDDB更改数据分区的只读实例个数成功之后, UDDB实例的状态变成"Running"(正常运行中); 如果更改过程中出现异常, 状态变成"Abnormal"(异常运行中)或者"Error"(运行错误)

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UDDBId|string|UDDB资源id|**Yes**|
|SlaveCount|string|每个数据节点的只读实例个数, 取值必须>=0|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ChangeUDDBSlaveCount
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=QCIvSqYb
&DataNodeSlaveCount=tBKPsXCS
&ProjectId=pnUVjMHA
```

# Response Example
```
{
    "Action": "ChangeUDDBSlaveCountResponse", 
    "RetCode": 0
}
```

