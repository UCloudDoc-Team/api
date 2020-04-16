# 获取资源支持监控指标信息-DescribeResourceMetric

获取资源支持监控指标信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceType|string|资源类型 支持如下类型：dbaudit：数据库审计；docker:容器服务；docker_node:容器服务节点；eip：弹性IP；fortress:堡垒机；hybridcloud_lan:混合云局域网；hybridcloud_port:混合云交换机端口；hybridcloud_port_sum:混合云外网总出口；mq：消息队列；natgw：NAT网关；phost：物理云主机；sharebandwidth：共享带宽；uaiservice：AI在线服务；ucdn：云分发；udb：云数据库；uddb：分布式数据库；uddbac：UDDB分析节点；uddbmd：分布式数据库中间件；uddbnode：分布式数据库节点；udisk：云硬盘；udisk_rssd：RSSD云硬盘；udisk_ssd：SSD云硬盘（数据盘）；udisk_sys：普通云硬盘（系统盘）；udpn：高速通道；udset:私有专区资源池；udset_uhost:资源池主机；udw：云数据仓库；udw_node:云数据仓库节点；ues：ES服务；ues_node：elasticsearch服务节点；ufile：对象存储；ufs：文件存储；ugaa：全球动态加速；ugc：通用计算；uhadoop：托管Hadoop集群；uhadoop_host：托管Hadoop集群；uhost：云主机；ukafka：Kafka消息队列；ukafka_host：分布式消息节点；ukv：容量型KV存储；ulb：负载均衡；ulb-server：真实服务节点；ulb-vserver：虚拟服务节点；umem：云内存存储；umemcache：单机版memcache；upath：加速线路；uredis：云内存存储；utsdb：时序数据库；vpntunnel：vpn隧道；vserver：虚拟服务节点；各产品支持监控项，请查看：https://docs.ucloud.cn/api/umon-api/get_metric|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|指标信息集合|**Yes**|

## DescribeResourceMetricResponse
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Unit|string|单位：bit Byte Kb KB Mb MB Gb GB Tb TB Pb PB Eb EB iops bps Bps Kbps KBps Mbps MBps Gbps GBps Tbps TBps 个 个/s 次 次/s 千次/s 万次/s % s ms us bool ‱ 个/min 个/核 个/10s bytes/10s MB/s dbm min|**Yes**|
|ConversionFactor|int|保留字段|**Yes**|
|Type|int|指标类型（暂时没有意义）|**Yes**|
|MetricGroup|string|监控指标组|**Yes**|
|SupportAlarm|string|是否支持告警：Yes\|No|**Yes**|
|AlarmRange|string|告警阈值设置的有效范围|**Yes**|
|Frequency|int|告警频率|**Yes**|
|MetricId|int|监控项id|**Yes**|
|CompareOption|array|比较方法：GE大于等于\|LE小于等于|**Yes**|
|MetricName|string|指标名字|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeResourceMetric
&ResourceType=uhost
```

# Response Example
```
{
    "Action": "DescribeResourceMetricResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "CompareOption": [
                "GE"
            ], 
            "SupportAlarm": "Yes", 
            "MetricId": 8000, 
            "Frequency": 60, 
            "AlarmRange": {
                "max": 100, 
                "min": 50
            }, 
            "MetricGroup": "", 
            "ConversionFactor": 0, 
            "Type": "Number", 
            "Unit": "%", 
            "MetricName": "CPUUtilization"
        }
    ]
}
```

