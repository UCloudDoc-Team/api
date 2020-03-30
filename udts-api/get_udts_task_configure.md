# 获取任务配置-GetUDTSTaskConfigure

获取任务配置

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TaskId|string|任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Data|object|详细配置信息|No|

## ConfigData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TaskId|string|任务 ID|No|
|Name|string|任务名称|No|
|Type|string|任务类型, full全量, incremental增量，full+incremental全量+增量。|No|
|MaxRetryCount|int|最大失败重试次数|No|
|Source|object|Source |No|
|Target|object|Target |No|

## Source
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DataType|string|源数据类型可以是 mysql, tidb, csv, oracle, udb-mysql。目的数据类型可以是 mysql, tidb, udb-mysql, udw.|**Yes**|
|NWType|string|网络类型|**Yes**|
|BandwidthLimit|int|设置的最大的速率，单位MB/s，公网/专线(0, 56]，用户网(0, 1024]，不填/超过默认是峰值|No|
|CSVNode|object|当 DataType 为csv的时候使用。|No|
|MySQLNode|object|当 DataType 为mysql的时候使用。|No|
|TiDBNode|object|当 DataType 为tidb的时候使用。|No|
|UDWNode|object|当 DataType 为 udw 的时候使用。|No|
|RedisNode|object|当 DataType 为 redis 的时候使用|No|
|UFileNode|object|当 DataType 为 ufile 的时候使用。|No|
|IsDedicatedLine|string|是否为专线迁移|No|

## CSVNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|URL|string|数据路径|**Yes**|
|KeepExistData|bool|数据迁移的时候是否保留原有数据， 默认为 false 不保留|No|
|DupAction|string|当加载重复数据的时候所采取的行为，有效值有 ignore - 忽略， replace - 替换， update - 更新。 默认为replace|No|
|Columns|string|如果 DupAction 为 ignore或者replace,  并且需要调整列的顺序的时候使用。 以逗号分割的列名字符串。|No|
|UpdatePolicy|array|如果 DupAction 为 update, 并且不想用CSV数据完整替换原有数据的时候使用。|No|
|SetPolicy|array|如果 DupAction 为 update, 并且在插入数据的同时想给一些列赋予特定的值的时候使用。|No|

## MySQLNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DataBase|string|DB 名字， 长度不超过63个字符|**Yes**|
|Host|string|数据库地址，长度不能超过 60个字符|**Yes**|
|Port|int|数据库端口，端口范围 1-65535|**Yes**|
|User|string|数据库用户名，长度不能超过 32个字符|**Yes**|
|Password|string|数据库密码，长度不起来32个字符|**Yes**|
|Table|string|表名， 长度不超过64个字符|No|
|VPCId|string|VPC 资源ID, 只有当 Host 为 UCloud 用户内网地址的时候需要提供。|No|
|SubnetId|string|子网 ID, 只有当 Host 为 UCloud 用户内网地址并且源目属于不同的地域的时候需要提供。|No|
|DataRegion|string|地域，只有当 Host 为 UCloud 用户内网地址的时候需要提供|No|
|SyncData|object|增量同步数据|No|

## TiDBNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DataBase|string|DB 名字， 长度不超过63个字符|**Yes**|
|Host|string|数据库地址，长度不能超过 60个字符|**Yes**|
|Port|int|数据库端口，端口范围 1-65535|**Yes**|
|User|string|数据库用户名，长度不能超过 32个字符|**Yes**|
|Password|string|数据库密码，长度不起来32个字符|**Yes**|
|Table|string|表名， 长度不超过64个字符|No|
|VPCId|string|VPC 资源ID, 只有当 Host 为 UCloud 用户内网地址的时候需要提供。|No|
|SubnetId|string|子网 ID, 只有当 Host 为 UCloud 用户内网地址并且源目属于不同的地域的时候需要提供。|No|
|DataRegion|string|地域，只有当 Host 为 UCloud 用户内网地址的时候需要提供|No|

## UDWNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DataBase|string|DB 名字， 长度不超过63个字符|**Yes**|
|Host|string|数据库地址，长度不能超过 60个字符|**Yes**|
|Port|int|数据库端口，端口范围 1-65535|**Yes**|
|User|string|数据库用户名，长度不能超过 32个字符|**Yes**|
|Password|string|数据库密码，长度不起来32个字符|**Yes**|
|VPCId|string|VPC 资源ID, 只有当 Host 为 UCloud 用户内网地址的时候需要提供。|**Yes**|
|DataRegion|string|地域|**Yes**|
|SubnetId|string|子网 ID, 只有当源目属于不同的地域的时候需要提供。|No|

## RedisNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Address|string|数据库地址，只填写主(master)地址，集群模式下，多个地址用 ; 相连|**Yes**|
|Type|string|redis模式|**Yes**|
|Password|string|redis密码|No|
|IsRump|string|Redis2Redis全量迁移是否使用rump，默认是dump-restore|No|
|VPCId|string|数据库所在机器的 VPCId, 只有内网跨域迁移的时候需要提供|No|
|SubnetId|string|子网 ID, 只有当 Host 为 UCloud 用户内网地址并且源目属于不同的地域的时候需要提供|No|
|DataRegion|string|数据库所在的地域。 只有当 Host 为 UCloud 用户内网地址的时候需要提供|No|

## UFileNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BucketName|string|Bucket 名称|**Yes**|
|PrivateKey|string|私钥|**Yes**|
|PublicKey|string|公钥|**Yes**|
|DataRegion|string|地域|**Yes**|
|Prefix|string|前缀，utf-8编码，默认为空字符串|No|
|DomainName|string|用户自定义域名|No|

## PolicyData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Column|string|列名|**Yes**|
|Type|string|可选值为 CSVData, Function, Fixed|**Yes**|
|Data|string|与上面类型对应的值， 比如“1”， “now()”, "Nash".|**Yes**|

## SyncData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BinlogName|string|Binlog 文件名， 长度不超过128字符|**Yes**|
|BinlogPos|int|Binlog Pos|**Yes**|
|ServerId|int|分配给UDTS task的server ID, 必须在MySQL集群中唯一|**Yes**|
|BinlogGTID|string|GTID|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUDTSTaskConfigure
&ProjectId=org-hin123
&TaskId=udts-xavwe
```

# Response Example
```
{
    "Action": "GetUDTSTaskConfigureResponse", 
    "Message": "", 
    "Data": {
        "Source": {
            "DataType": "csv", 
            "CSVNode": {
                "URL": "http://xxxxxx.cn-bj.ufileos.com/test.csv", 
                "DupAction": "update", 
                "SetPolicy": [
                    {
                        "Column": "name", 
                        "Data": "now()", 
                        "Type": "Function"
                    }, 
                    {
                        "Column": "value", 
                        "Data": "1", 
                        "Type": "CSVData"
                    }, 
                    {
                        "Column": "id", 
                        "Data": "0", 
                        "Type": "CSVData"
                    }
                ], 
                "KeepExistData": true, 
                "UpdatePolicy": [
                    {
                        "Column": "name", 
                        "Data": "aaa", 
                        "Type": "Fixed"
                    }, 
                    {
                        "Column": "value", 
                        "Data": "1", 
                        "Type": "CSVData"
                    }, 
                    {
                        "Column": "id", 
                        "Data": "0", 
                        "Type": "CSVData"
                    }
                ]
            }
        }, 
        "Type": "full", 
        "Name": "xxxxx", 
        "TaskId": "udts-xavwe", 
        "Target": {
            "DataType": "mysql", 
            "MySQLNode": {
                "VPCId": "uvnet-iqi21o", 
                "Database": "test", 
                "Host": "10.19.64.15", 
                "User": "root", 
                "Table": "t_csv", 
                "Port": 3306, 
                "DataRegion": "cn-bj2"
            }
        }
    }, 
    "RetCode": 0
}
```

