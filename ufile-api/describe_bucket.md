# 获取Bucket信息-DescribeBucket

获取Bucket的描述信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|如果提供此参数，则获取相应地域下所有空间的空间名称|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BucketName|string|待获取Bucket的名称，若不提供，则获取所有Bucket|No|
|Offset|int|获取所有Bucket列表的偏移数目，默认为0|No|
|Limit|int|获取所有Bucket列表的限制数目，默认为20|No|

```
注意：如果提供了参数BucketName，则参数Offset和Limit失效。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|Bucket的描述信息 参数见 UFileBucketSet|No|

## UFileBucketSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BucketName|string|Bucket名称|No|
|BucketId|string|Bucket的ID|No|
|Domain|array|Bucket的域名集合 参数见 UFileDomainSet|No|
|CdnDomainId|array|与Bucket关联的CND加速域名的ID列表|No|
|Type|string|Bucket访问类型|No|
|CreateTime|int|Bucket的创建时间|No|
|ModifyTime|int|Bucket的修改时间|No|
|Biz|string|Bucket所属业务, general或vod或udb general: 普通业务； vod: 视频云业务; udb: 云数据库业务|No|
|Region|string|Bucket所属地域|No|
|Tag|string|所属业务组|No|
|HasUserDomain|int|是否存在自定义域名。0不存在，1存在，2错误|No|

## UFileDomainSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Src|array|源站域名|No|
|Cdn|array|UCDN加速域名|No|
|CustomSrc|array|用户自定义源站域名|No|
|CustomCdn|array|用户自定义CDN加速域名|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeBucket
&BucketName=blue
&Region=cxqbTMaU
&Region=cn-zj
```

# Response Example
```
{
    "Retcode": 0, 
    "Aciton": "DescribeBucketResponse", 
    "DataSet": [
        {
            "Domain": {
                "Src": [
                    "blue.ufile.ucloud.cn"
                ], 
                "Cdn": [
                    "blue.ufile.ucloud.com.cn"
                ], 
                "CustomCdn": [], 
                "CustomSrc": []
            }, 
            "HasUserDomain": 1, 
            "BucketId": "ufile-xxx", 
            "Region": "cn-bj2", 
            "CreateTime": 1409736300, 
            "Tag": "dddd", 
            "Biz": "general", 
            "BucketName": "blue", 
            "ModifyTime": 1409736300, 
            "Type": "public", 
            "CdnDomainId": [
                "ucdn-xxx"
            ]
        }
    ]
}
```

