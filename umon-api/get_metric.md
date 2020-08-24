# 获取监控数据-GetMetric

获取监控数据

## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetMetric)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetMetric`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
|**Region**|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|**Zone**|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|**ProjectId**|string|项目ID，不填为默认项目。子账户必须填写项目ID|No|
|**ResourceType**|string|资源类型|**Yes**|
|**MetricName.n**|string|指标名称（不同ResourceType对应不同的MetricName）|**Yes**|
|**ResourceId**|string|资源Id（目前除sharebandwidth可以不传入ResourceId外，其他资源必须传入，sharebandwidth不传入会默认使用获取到的第一个资源Id）|No|
|**TimeRange**|int|拉取最近多少秒的监控数据，默认1小时，即3600；最大1个月|No|
|**BeginTime**|int|起始时间unixtimestamp，若传入TimeRange，此项忽略|No|
|**EndTime**|int|结束时间unixtimestamp，若传入TimeRange，此项忽略；若只传入BeginTime，此项默认为当前时间|No|

> 注解：GetMetric获取的数据，根据所选时间段不同，会返回不同的粒度，粒度如下：
> ---- 0-2小时：1分钟
> ---- 2小时-1天(24小时)：5分钟
> ---- 1天-15天：1小时
> ---- 15天以上：12小时 

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
|**RetCode**|int|返回码|**Yes**|
|**Action**|string|操作名称|**Yes**|

#### ResrouceType:uhost

|参数|描述信息|单位|
|:---|:---|:---|
|**CPUUtilization**|CPU使用率|%|
|**IORead**|磁盘读流量|Bps|
|**IOWrite**|磁盘写流量|Bps|
|**DiskReadOps**|磁盘读次数|次/s|
|**DiskWriteOps**|磁盘写次数|次/s|
|**NICIn**|网卡入带宽|bps|
|**NICOut**|网卡出带宽|bps|
|**NetPacketIn**|网卡入包量|个/s|
|**NetPacketOut**|网卡出包量|个/s|

#### 云主机系统级监控（需安装监控代理）

|参数|描述信息|单位|
|:---|:---|:---|
| **MemUsage**              | 内存使用率           | %     |
| **RootSpaceUsage**        | 系统盘使用率          | %     |
| **DataSpaceUsage**        | 数据盘使用率          | %     |
| **ReadonlyDiskCount**     | 只读磁盘个数          | 个     |
| **RunnableProcessCount**  | 运行进程数目          | 个     |
| **BlockProcessCount**     | 阻塞进程数目          | 个     |
| **ProcessCount**          | 进程总数            | 个     |
| **TcpConnectCount**       | TCP连接数(仅Linux)  | 个     |
| **LoadAvg1m**             | 1分钟负载(仅Linux)   | /     |
| **LoadAvg5m**             | 5分钟负载(仅Linux)   | /     |
| **LoadAvg15m**            | 15分钟负载(仅Linux)  | /     |

#### ResrouceType:phost

|参数|描述信息|单位|
|:---|:---|:---|
| **RootSpaceUsage**        | 系统盘使用率          | %     |
| **DataSpaceUsage**        | 数据盘使用率          | %     |
| **LoadAvg1m**             | 1分钟负载(仅Linux)   | /     |
| **LoadAvg5m**             | 5分钟负载(仅Linux)   | /     |
| **LoadAvg15m**            | 15分钟负载(仅Linux)  | /     |
| **MemUsage**              | 内存使用率           | %     |
| **MemFree**               | 空闲内存             |Kb|
| **TcpConnectCount**       | TCP连接数(仅Linux)  | 个     |
| **ProcessCount**          | 进程总数            | 个     |
| **ReadonlyDiskCount**     | 只读磁盘个数          | 个     |
| **RunnableProcessCount**  | 运行进程数目          | 个     |
| **BlockProcessCount**     | 阻塞进程数目          | 个     |
| **CPUUtilization**         |CPU使用率             |%       |
| **IORead**                 |磁盘读流量             |Bps|
| **DiskReadOps**            |磁盘读次数             |次/s|
|**NICIn**                   |网卡入带宽             |bps|
|**UpmDiskHealthCheck**|物理云磁盘健康状态检查||
|**GPUTemp**|GPU最高温度|℃|

#### ResrouceType:docker

|参数|描述信息|单位|
|:---|:---|:---|
|**CPUUtilization**|CPU使用率|%|
|**IORead**|磁盘读流量|Bps|
|**IOWrite**|磁盘写流量|Bps|
|**MemUsage**|内存使用率|%|
|**NICIn**|网卡入带宽|bps|
|**NICOut**|网卡出带宽|bps|
|**NetPacketIn**|网卡入包量|个/s|
|**NetPacketOut**|网卡出包量|个/s|

#### ResourceType:eip

|参数|描述信息|单位|
|:---|:---|:---|
| **NetworkOut**       | 网络出口   | bps          |
| **NetworkIn**        | 网络入口   | bps          |
| **NetworkOutUsage**  | 出口使用率  | %            |
| **NetworkInUsage**   | 入口使用率  | %            |

#### ResourceType:sharebandwidth

|参数|描述信息|单位|
|:---|:---|:---|
|**BandIn**|入口带宽|bps|
|**BandOut**|出口带宽|bps|

#### ResourceType:vrouter（该业务已下线，不再支持该资源的监控数据获取）

#### ResourceType:ulb

|参数|描述信息|单位|
|:---|:---|:---|
|**TotalNetworkOut**|总网络出口|b/s|

#### ResourceType:ulb-vserver

|参数|描述信息|单位|
|:---|:---|:---|
|**CurrentConnections**|VServer连接数|个|
|**NewConnections**|vserver每秒新建连接数|个/s|
|**UlbVserverHrsp2xx**|VServer每秒返回2XX的次数|个/s|
|**UlbVserverHrsp3xx**|VServer每秒返回3XX的次数|个/s|
|**UlbVserverHrsp4xx**|VServer每秒返回4XX的次数|个/s|
|**UlbVserverHrsp5xx**|VServer每秒返回5XX的次数|个/s|
|**UlbVserverHrspOther**|VServer每秒返回其它状态码的次数|个/s|

#### ResourceType:udisk

|参数|描述信息|单位|
|:---|:---|:---|
|**IOPSRead**|UDisk磁盘读次数|次/s|
|**IOPSWrite**|UDisk磁盘写次数|次/s|
|**BytesRead**|UDisk磁盘读带宽|Bps|
|**BytesWrite**|UDisk磁盘写带宽|Bps|

#### ResourceType:udisk_ssd

|参数|描述信息|单位|
|:---|:---|:---|
|**IOPSRead**|UDisk磁盘读次数|次/s|
|**IOPSWrite**|UDisk磁盘写次数|次/s|
|**BytesRead**|UDisk磁盘读带宽|Bps|
|**BytesWrite**|UDisk磁盘写带宽|Bps|

#### ResourceType:udb

|参数|描述信息|单位|
|:---|:---|:---|
|**DiskUsage**|磁盘使用率|%|
|**CPUUtilization**|CPU使用率|%|
|**MemSize**|内存大小|MB|
|**ConnectionCount**|连接数|个|
|**QPS**|QPS|次/s|
|**DeleteQPS**|删除QPS|次/s|
|**InsertQPS**|插入QPS|次/s|
|**SelectQPS**|查询QPS|次/s|
|**UpdateQPS**|更新QPS|次/s|
|**SlaveDelay**|从库同步延迟|s|
|**MemUsage**|内存使用率|%|
|**ExpensiveQuery**|慢查询|个|
|**SynchronizationError**|主从同步|个|
|**BackupFailed**|备份失败|次|
|**PingErrorCount**|db连通情况|个|
|**ReplaceQPS**|ReplaceQPS|次/s|
|**IOOps**|IO平均读写次数|次/s|
|**IO**|IO平均读写字节数|Bps|
|**AbReboot**|异常重启|次|
|**CoreFailure**|核心管理功能失效|次|
|**CPUCoreUsed**|CPU使用量(核数)|个|
|**DumpFailure**|DB备份导出失败|次/s|
|**SandboxMemory**|DB系统总内存|MB|
|**SandboxCache**|DB系统总缓存|MB|
|**ServiceAvailability**|DB可用性错误||
|**TPS**|每秒事务数|次/s|
|**ConnectionMaxFlag**|连接数是否打满||
|**HAHealthState** |高可用状态是否异常|bool|
|**ActiveMemoryRatio**|内存活跃占比|%|
|**HASyncDelay** |高可用主备数据同步延时|s|
|**IDHASlaveError** |高可用主从是否异常| bool|

#### ResourceType:umem（分布式memcache、分布式redis）

|参数|描述信息|单位|
|:---|:---|:---|
|**InstanceUsage**|使用量|KB|
|**InstanceCount**|记录数|个|
|**InstanceGetQPS**|GetQPS|次/s|
|**InstanceSetQPS**|SetQPS|次/s|
|**InstanceDelQPS**|DelQPS|次/s|
|**QPS**|总QPS|次/s|
|**InstanceGetHit**|命中数|次/s|
|**InstanceAddQPS**|AddQPS（分布式memcache特有的监控）|次/s|
|**InstanceReplaceQPS**|ReplaceQPS（分布式memcache特有的监控）|次/s|
|**InstanceAppendQPS**|AppendQPS（分布式memcache特有的监控）|次/s|
|**InstancePrependQPS**|PrependQPS（分布式memcache特有的监控）|次/s|
|**InstanceIncrQPS**|IncrQPS|次/s|
|**InstanceDecrQPS**|DecrQPS|次/s|
|**InstanceGetHitRate**|命中率|%|
|**PingErrorCount**|Ping错误数（分布式memcache特有的监控）|个|
|**Usage**|使用率|%|
|**BlockMaxUsage**|最大块内存使用率|%|
|**RedisAvgLoad**|Redis平均负载|%|
|**RedisSiglenodeMaxload**|Redis单点最高负载|%|
|**UMemInstanceConnCount**|连接数量|次|
|**RequestTimeoutErrorCount**|请求超时次数|次|
|**OtherErrorCount**|其他错误（分布式memcache特有的监控）|次|
|**RequestDelayErrorCount**|延迟次数|次|

#### ResourceType:umemcache（单机版memcache）

|参数|描述信息|单位|
|:---|:---|:---|
|**InstanceUsage**|使用量|KB|
|**InstanceUsageRate**|存储空间使用率|%|
|**InstanceConnCount**|当前连接数|个|
|**InstanceKeyNum**|总key个数|个|
|**InstanceBytesRead**|输入流量|Bps|
|**QPS**|总QPS|次/s|
|**InstanceSetQPS**|SetQPS|次/s|
|**InstanceGetQPS**|GetQPS|次/s|
|**InstanceGetNum**|get操作数|次|
|**InstanceDeleteNum**|delete操作数|次|
|**InstanceIncNum**|incr操作数|次|
|**InstanceSetNum**|set操作数|次|
|**InstanceTouchNum**|touch操作数|次|
|**InstanceCasNum**|cas操作数|次|
|**InstanceCpuUsage**|CPU负载|%|

#### ResourceType:uredis

|参数|描述信息|单位|
|:---|:---|:---|
| **InstanceUsage**            | 使用量             | KB  |
| **URedisInstanceConnCount**  | 连接数             | 个     |
| **QPS**                      | 总QPS            | 次/s   |
| **InstanceKey**              | Key数量           | 个     |
| **InstanceGetHit**           | 命中数             | 个     |
| **InstanceGetHitRate**       | 命中率             | %     |
| **InstanceTotalGetQPS**      | 总GetQPS         | 次/s   |
| **InstanceTotalSetQPS**      | 总SetQPS         | 次/s   |
| **InstanceListQPS**          | ListQPS         | 次/s   |
| **InstanceStringQPS**        | StringQPS       | 次/s   |
| **InstanceHashQPS**          | HashQPS         | 次/s   |
| **InstanceSetQPS**           | SetQPS          | 次/s   |
| **InstanceZsetQPS**          | ZsetQPS         | 次/s   |
| **InstanceHyperloglogQPS**   | HyperloglogQPS  | 次/s   |
| **InstancePubsubQPS**        | PubsubQPS       | 次/s   |
| **InstanceTransactionQPS**   | TransactionQPS  | 个     |
| **RedisSinglenodeMaxload**   | 单节点最大负载         | %     |
| **NICIn**                    | 入带宽             | Bps   |
| **NICOut**                   | 出带宽             | Bps   |
| **RedisAvgCPULoad**          | Redis平均负载         | %     |

#### ResourceType:udpn

UDPN产品获取监控数据需配合Region字段使用，Region表示获取该专线在某一地域的出口流量

|参数|描述信息|单位|
|:---|:---|:---|
|**BandOut**|出带宽|b/s|
|**BandOutMax**|峰值出带宽|b/s|
|**BandOutUsage**|带宽使用率|％|
|**BandOutMaxUsage**|峰值带宽使用率|％|

#### ResourceType:natgw

|参数|描述信息|单位|
|:---|:---|:---|
|**BandOut**|网络出口|bps|
|**BandIn>**|网络入口|bps|
|**FlowOut**|出口流量|Byte|
|**FlowIn**|入口流量|Byte|
|**PacketOut>-**|出包量>|个|
|**PacketIn>--**|入包量>|个|

#### ResourceType:uhadoop

|参数|描述信息|单位|
|:---|:---|:---|
|**HdfsUsage**|hdfs使用百分比|%|
|**MemoryUsage**|已用内存百分比|%|
|**AppsRunning**|正在运行中的app数量|个|
|**HdfsTotal**|hdfs总容量|GB|
|**HdfsUsed**|hdfs当前所用容量|GB|
|**HdfsAvailable**|hdf当前可用容量|GB|
|**AppsSubmitted**|App提交总数|个|
|**AppsCompleted**|App已完成总数|个|
|**AppsPending**|等待中的app数量|个|
|**AppsFailed**|失败app数量|个|
|**AppsKilled**|终止app数量|个|
|**AvailableMem**|可用内存|MB|
|**AllocatedMem**|已分配内存|MB|
|**TotalMem**|总可用内存|MB|
|**ContainersAllocated**|已分配的container|个|
|**ContainersPending**|等待状态的container|个|
|**AvailableVirtualCores**|可用core|个|
|**AllocatedVirtualCores**|已分配的core|个|
|**TotalVirtualCores**|Core总数|个|

#### ResrouceType:uhadoop_host

|参数|描述信息|单位|
|:---|:---|:---|
|**CPUUtilization**|CPU使用率|%|
|**IORead**|磁盘读流量|Bps|
|**IOWrite**|磁盘写流量|Bps|
|**DiskReadOps**|磁盘读次数|次/s|
|**DiskWriteOps**|磁盘写次数|次/s|
|**NICIn**|网卡入带宽|bps|
|**NICOut**|网卡出带宽|bps|
|**NetPacketIn**|网卡入包量|个/s|
|**NetPacketOut**|网卡出包量|个/s|
|**MemUsage**|内存使用率|%|
|**DataSpaceUsage**|数据盘磁盘空间使用率|%|
|**RootSpaceUsage**|系统盘磁盘空间使用率|%|

#### ResrouceType:ukafka

|参数|描述信息|单位|
|:---|:---|:---|
|**BytesInPerSec**|每秒流入数据|Bps|
|**BytesOutPerSec**|每秒流出数据|Bps|
|**MessagesInPerSec**|MessagesInPerSec|个/s>|
|**FailedFetchRequestsPerSec**|消费者失败请求|次/s|
|**FailedProduceRequestsPerSec**|生产者失败请求|次/s|
|**BytesRejectedPerSec**|Broker拒绝的消息|Bps|
|**LeaderFeq**|leader选举频率|ms|
|**ControllerCount**|controller存活数目|个|
|**ProducerTimeout**|producer请求响应时间|ms|
|**ProducerQPS**|producerQPS|次/s|
|**ConsumerTimeout**|consumer请求响应时间|ms|
|**ConsumerQPS**|consumerQPS|次/s|
|**ZkNumAliveConnection**|zk当前活跃连接数|个|
|**ZkMaxRequestLatency**|zk最大请求延时  |ms|
|**ZkAvgRequestLatency**|zk平均请求延时  |ms|
|**ZkMinRequestLatency**|zk最小请求延时  |ms|
|**ZkPacketsSent**|zk发送响应数|个|
|**ZkPacketsReceived**|zk接收响应数|个|
|**ZkOutstandingRequests**|zk待处理连接数|个|
|**ZkWatchCount**|watches的数量|个|
|**ZkNodeCount**|znodes的数量|个|

#### ResrouceType:ukafka_host

|参数|描述信息|单位|
|:---|:---|:---|
|**MessagesInPerSec**|每秒流入消息个数|个/s>|
|**BytesInPerSec**|每秒流入数据|Bps|
|**BytesOutPerSec**|每秒流出数据|Bps|
|**ReplicaMaxLag**|Follower落后Leader的最大消息量|个|
|**PartitionCount**|分布在该节点上的分区总数|个|
|**LeaderCount**|分布在该节点上的leader分区总数|个|
|**UnderReplicatedPartitions**|未复制的分区总数|个|
|**IsrExpandsPerSec**|ISR扩大速率|个／s|
|**IsrShrinksPerSec**|ISR收缩速率|个／s|
|**ActiveControllerCount**|管理节点个数|个|
|**OfflinePartitionsCount**|离线分区总数|个|
|**FailedFetchRequestsPerSec**|消费者失败请求|次/s|
|**FailedProduceRequestsPerSec**|生产者失败请求|次/s|
|**BytesRejectedPerSec**|Broker拒绝的消息|Bps|
|**ProducerTimeout**|producer请求响应时间|ms|
|**ProducerQPS**|ProducerQPS|次/s|
|**ConsumerTimeout**|consumer请求响应时间|ms|
|**ConsumerQPS**|consumerQPS|次/s|
|**ZkNumAliveConnection**|zk当前活跃连接数|个|
|**ZkMaxRequestLatency**|zk最大请求延时  |ms|
|**ZkAvgRequestLatency**|zk平均请求延时  |ms|
|**ZkMinRequestLatency**|zk最小请求延时  |ms|
|**ZkPacketsSent**|zk发送响应数|个|
|**ZkPacketsReceived**|zk接收响应数|个|
|**ZkOutstandingRequests**|zk待处理连接数|个|
|**ZkWatchCount**|watches的数量|个|
|**ZkNodeCount**|znodes的数量|个|
|**CPUUtilization**|CPU使用率|%|
|**IORead**|磁盘读流量|Bps|
|**IOWrite**|磁盘写流量|Bps|
|**DiskReadOps**|磁盘读次数|次/s|
|**DiskWriteOps**|磁盘写次数|次/s|
|**NICIn**|网卡入带宽|bps|
|**NICOut**|网卡出带宽|bps|
|**NetPacketIn**|网卡入包量|个/s|
|**NetPacketOut**|网卡出包量|个/s|
|**MemUsage**|内存使用率|%|
|**DataSpaceUsage**|数据盘磁盘空间使用率|%|
|**RootSpaceUsage**|系统盘磁盘空间使用率|%|

#### ResrouceType:udw

|参数|描述信息|单位|
|:---|:---|:---|
|**UdwQPS**|每秒查询率|次/s>|
|**UdwDbConnections**|数据库连接数|个|
|**UdwDiskUsage**|集群磁盘容量使用率|%|

#### ResrouceType:udw_node

|参数|描述信息|单位|
|:---|:---|:---|
|**UdwNodeCpuUsage**|节点CPU使用率|%|
|**UdwNodeMemoryUsage**|节点内存利用率|%|
|**UdwNodeNetworkOut**|节点网络带宽出量|Bps|
|**UdwNodeNetworkIn**|节点网络带宽入量|Bps|
|**UdwNodeNetOutPackets**|节点网卡出包量|个/s|
|**UdwNodeNetInPackets**|节点网卡入包量|个/s|
|**UdwNodeDiskUsage**|节点磁盘使用率|%|
|**UdwNodeDiskIORead**|节点磁盘读吞吐量|Bps|
|**UdwNodeDiskIOWrite**|节点磁盘写吞吐量|Bps|
|**UdwNodeDiskReadCount**|节点磁盘读次数|次|
|**UdwNodeDiskWriteCount**|节点磁盘写次数|次|

#### ResrouceType:ufile

|参数|描述信息|单位|
|:---|:---|:---|
| **BucketDownloadFlow**       | 下载流量         | Byte  |
| **BucketUploadFlow**         | 上传流量         | Byte  |
| **BucketTotalStorage**       | 总存储量         | Byte  |
| **BucketUploadInnerFlow**    | 内网上传流量       | Byte  |
| **BucketDownloadInnerFlow**  | 内网下载流量       | Byte  |
| **BucketUploadCount**        | 上传请求数        | 次     |
| **BucketDownloadCount**      | 下载请求数        | 次     |
| **BucketDeleteCount**        | 删除请求数        | 次     |
| **Bucket5xxError**           | 服务端错误        | 次     |
| **BucketCdnFlow**            | CDN回源流量      | Byte  |

#### Response Item

|参数|描述信息|单位|
|:---|:---|:---|
|**Timestamp**|Integer|时间戳|
|**Value**|Float|监控数据|

## 示例

### 请求示例

```
https://api.ucloud.cn/?Action=GetMetric
&Region=cn-bj2
&Zone=cn-bj2-04
&ResourceType=uhost
&ResourceId=uhost-xxx
&MetricName.1=NetPacketIn
&MetricName.0=NetPacketOut
&BeginTime=1431505992
&EndTime=1431506592
```

### 响应示例

```json
{
    "Action": "GetMetricResponse", 
    "DataSets": {
        "NetPacketOut": [
            {
                "Timestamp": 1431506100, 
                "Value": 0
            }, 
            {
                "Timestamp": 1431506400, 
                "Value": 0
            }
        ], 
        "NetPacketIn": [
            {
                "Timestamp": 1431506100, 
                "Value": 0
            }, 
            {
                "Timestamp": 1431506400, 
                "Value": 0
            }
        ]
    }, 
    "RetCode": 0
}
```
