# 创建Bucket-CreateBucket

创建Bucket

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BucketName|string|待创建Bucket的名称，具有全局唯一性|**Yes**|
|Type|string|Bucket访问类型，public或private; 默认为private|No|

```
－BucketName BucketName参数将构成域名的一部分(与Bucket默认关联的域名为<BucketName>.ufile.ucloud.cn)，必须具有全局唯一性。 BucketName参数必须符合Bucket名称规范,规范如下: (1) 长度在3~63字节之间； (2) 可以由多个标签组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结尾的字符只能是小写字母或数字； (3) 不可以是IP地址。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BucketName|string|已创建Bucket的名称|No|
|BucketId|string|已创建Bucket的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateBucket
&BucketName=blue
&Type=public
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "CreateBucketResponse", 
    "BucketId": "ufile-qs20fr", 
    "Retcode": 0, 
    "BucketName": "blue"
}
```

