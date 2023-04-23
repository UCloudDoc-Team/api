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
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取      | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
|**Region**|string|地域，注意Region和Zone必填其中一个。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|**Zone**|string|可用区，注意Region和Zone必填其中一个。参见 [可用区列表](api/summary/regionlist)|No|
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

#### ResourceType:uhost

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
| **TcpConnectCount**       | TCP连接数(仅Linux)   | 个     |
| **LoadAvg1m**             | 1分钟负载(仅Linux)   | /     |
| **LoadAvg5m**             | 5分钟负载(仅Linux)   | /     |
| **LoadAvg15m**            | 15分钟负载(仅Linux)  | /     |
|**TcpSynSentCount**        | syn_sent状态tcp连接数 | 个   |
|**TcpSynRecvCount**        | syn_recv状态tcp连接数 | 个   |
|**TcpFinWait1Count**       | fin_wait1状态tcp连接数 | 个   |
|**TcpFinWait2Count**       | fin_wait2状态tcp连接数 | 个   |
|**TcpLastAckCount**        | last_ack状态tcp连接数  | 个   |
|**TcpClosingCount**        | closing状态tcp连接数   | 个   |
|**DiskWriteOps**           | 磁盘写次数             | 次/s |
|**TcpClosedCount**         | closed状态tcp连接数    | 个   |
|**CPUIOWait**              | CPU IOWait率          | %   |
|**TcpEstablishCount**      | establish状态tcp连接数 | 个   |
|**TcpTimeWaitCount**       | timewait状态tcp连接数  | 个   |
|**TcpCloseWaitCount**      | closewait状态tcp连接数 | 个   |
|**TcpListenCount**         | listen状态tcp连接数    | 个   |

#### ResourceType:phost

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
| **CPUUtilization**        | CPU使用率             |%       |
| **IORead**                | 磁盘读流量             |Bps|
| **DiskReadOps**           | 磁盘读次数             |次/s|
| **NICIn**                 | 网卡入带宽             |bps|
| **UpmDiskHealthCheck**    | 物理云磁盘健康状态检查||
| **GPUTemp**               | GPU最高温度 | ℃   |
| **IOWrite**               | 磁盘写吞吐  | Bps  |
| **DiskWriteOps**          | 磁盘写次数  | 次/s |
| **NetPacketIn**           | 网卡入包量  | 个/s |
| **NetPacketOut**          | 网卡出包量  | 个/s |

#### ResourceType:docker

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
| **EIPIdOutDropRate** | eipId出向丢包百分比 | %|
| **EIPIdInDropRate**  | eipId入向丢包百分比 | %|
| **FlowIn**            | 外网入流量 | Byte |
| **FlowOut**           | 外网出流量 | Byte |
| **EIPIdOutPPS**       | eipId出向发包速率 | 个/s |
| **EIPIdInPPS**        | eipId入向发包速率 | 个/s |
| **EIPIdOutDropPPS**   | eipId出向丢包速率 | 个/s |
| **EIPIdInDropPPS**    | eipId入向丢包速率 | 个/s |

#### ResourceType:sharebandwidth

|参数|描述信息|单位|
|:---|:---|:---|
| **BandIn**  | 入口带宽|bps|
| **BandOut** | 出口带宽|bps|
| **NetworkOutUsage** | 出口带宽使用率 | % |
| **NetworkInUsage**  | 入口带宽使用率 | % |

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
|**VServerQPS**|ulb7前端VServer的QPS|个/s|
|**RequestProxyRSDownPercent**|ulb7前端VServer节点失效百分比|%|
|**VServerRT**|ulb7端口维度的请求平均时延|ms|
|**VServerUpstreamRT**|ulb7端口维度的后端响应平均时延|ms|
|**NetPacketIn**|ulb4的vserver每秒入包量|个/s|
|**NetPacketOut**|ulb4的vserver每秒出包量|个/s|
|**BandIn**|ulb4的vserver每秒入流量|bps|
|**BandOut**|ulb4的vserver每秒出流量|bps|

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
|**MongoDBWTCacheDirtyUsage**|MongoDB WT缓存脏页占用率|%|
|**MongoDBGetMoreOPCountsTotal**|MongoDB累计getMore操作数|个|
|**IOAwait**|磁盘的IO响应时间|ms|
|**MongoDBWTReadFromDiskSizeTotal**|MongoDB WT磁盘读取累计数据量|Byte|
|**MongoDBCommandOPCountsTotal**|MongoDB累计执行管控命令操作数|个|
|**MongoDBWTWrittenIntoDiskSizeTotal**|MongoDB WT磁盘写入累计数据量|Byte|
|**MongoDBCurrentQueueTotal**|MongoDB读写等待队列总长度|个|
|**MongoDBCurrentQueueReaders**|MongoDB当前等待读队列长度|个|
|**MongoDBCurrentQueueWriters**|MongoDB当前等待写队列长度|个|
|**RWProxyQPS**|qps|次/s|
|**MongoDBActiveClientReaders**|MongoDB正在读的客户端数|个|
|**RWProxyConnCount**|连接数|个/min|
|**MongoDBActiveConns**|MongoDB活跃连接数|个|
|**MongoDBActiveClientWriters**|MongoDB正在写的客户端数|个|
|**RWProxyMemUtil**|内存使用率|%|
|**MongoDBWTCacheReadIntoSizeTotal**|MongoDB WT缓存读入累计数据量|Byte|
|**HAStandyDBDiskUsage**|高可用备主磁盘使用率|%|
|**MongoDBInsertOPCountsTotal**|MongoDB累计插入操作数|个|
|**RWProxyCpuUtil**|CPU使用率|%|
|**MongoDBWTCacheWrittenFromSizeTotal**|MongoDB WT缓存落盘累计数据量|Byte|
|**MongoDBQueryOPCountsTotal**|MongoDB累计查询操作数|个|
|**TPS**|每秒事务数|次/s|
|**MongoDBWTMaxSize**|MongoDB WT缓存总大小|Byte|
|**MongoDBUpdateOPCountsTotal**|MongoDB累计更新操作数|个|
|**MongoDBWTCacheUsage**|MongoDB WT缓存使用率|%|
|**MongoDBDeleteOPCountsTotal**|MongoDB累计删除操作数|个|

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
|**UmemProxyMaxLoad**|代理最高负载|%|
|**UmemProxyAvgLoad**|代理平均负载|%|

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
|**InstanceGetHitRate**|get命中率百分比|%|
|**InstanceDecrNum**|decr操作数|次|
|**InstanceBytesWritten**|输出流量|Bps|

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
| **URedisKeyEvicted**         | 历史累计逐出key总数   | 个 |
| **URedisMaxRt**              | 最大请求延迟         | us |
| **URedisAvgRt**              | 平均请求延迟         | us |
| **URedisFragmentationRatio** | 主备redis内存碎片率  | % |
| **URedisCurrentAofSize**     | 当前aof文件大小      | KB |
| **URedisSlaveSyncState**     | URedis主从同步状态   | bool |
| **Usage**                    | 内存使用量           | %  |
| **URedisExpiredKeys**        | 过期key             | 个 |
| **ConnectCountUsage**        | 连接数使用率         | %  |

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
|**ActiveNameNodeInSafemodCount**|active的NameNode处于safemode的个数|个|
|**LiveNodeCount**|探活的节点个数|个|
|**NameNodeInActiveCount**|NameNode是active的个数|个|
|**NameNodeInSafemodeCount**|NameNode处于safemode的个数|个|

#### ResourceType:uhadoop_host

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
|**BlockProcessCount**|阻塞进程数目|个|
|**ReadonlyDiskCount**|云主机只读磁盘个数|个|
|**LiveNodeCount**|探活的节点个数|个|
|**ProcessCount**|进程总数|个|
|**TcpConnectCount**|TCP连接数|个|
|**SysDiskIOUtil**|系统盘磁盘io使用率|%|
|**LoadAvg1m**|loadavg1分钟||
|**LoadAvg5m**|loadavg5分钟||
|**LoadAvg15m**|loadavg15分钟||
|**RunnableProcessCount**|运行进程数目|个|

#### ResourceType:ukafka

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
|**ConsumerListCount**|consumer队列中排队请求数|个|
|**kafkaLiveBrokerCount**|Kafka存活节点个数|个|
|**ZkNumAliveConnections**|zk当前活跃连接数|个|
|**ProducerListCount**|producer队列中排队请求数|个|

#### ResourceType:ukafka_host

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
|**NetPacketOut**|网卡出包量|个/s|
|**ProducerListCount**|producer队列中排队请求数|个|
|**ZkNumAliveConnections**|zk当前活跃连接数|个|
|**kafkaLiveBrokerCount**|Kafka存活节点个数|个|
|**ConsumerListCount**|consumer队列中排队请求数|个|

#### ResourceType:udw

|参数|描述信息|单位|
|:---|:---|:---|
|**UdwQPS**|每秒查询率|次/s>|
|**UdwDbConnections**|数据库连接数|个|
|**UdwDiskUsage**|集群磁盘容量使用率|%|
|**SegmentDown**|udw异常segment|个|
|**ServiceStatus**|udw服务状态||

#### ResourceType:udw_node

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
|**InstanceStoped**|udw停止节点|个|
|**SegmentDown**|udw异常segment|个|

#### ResourceType:ufile

|参数|描述信息|单位|
|:---|:---|:---|
| **BucketDownloadFlow**       | 下载流量         | Byte  |
| **BucketUploadFlow**         | 上传流量         | Byte  |
| **BucketTotalStorage**       | 标准存储量         | Byte  |
| **BucketUploadInnerFlow**    | 内网上传流量      | Byte  |
| **BucketDownloadInnerFlow**  | 内网下载流量      | Byte  |
| **BucketUploadCount**        | 上传请求数        | 次     |
| **BucketDownloadCount**      | 下载请求数        | 次     |
| **BucketDeleteCount**        | 删除请求数        | 次     |
| **Bucket5xxError**           | 服务端错误        | 次     |
| **BucketCdnFlow**            | CDN回源流量       | Byte  |
| **BucketDownLoadError**      | 下载超时错误数     | 次   |
| **BucketUploadError**        | 上传超时错误数     | 次   |
| **BucketRequestTotal**       | 总请求数          | 次   |
| **BucketArchiveRetrieval**   | 归档解冻量        | Byte |
| **BucketArchiveStorages**    | 归档存储量        | Byte |
| **Bucket2xxStatus**          | 2xx请求发生次数   | 次  |
| **BucketIaRetrieval**        | 低频取回量        | Byte |
| **Bucket4xxStatus**          | 4xx请求发生次数   | 次 |
| **BucketIaStorages**         | 低频存储量        | Byte |
| **BucketDownLoadSuccess**    | 下载成功数        | 次 |
| **BucketUploadSuccess**      | 上传成功数        | 次 |

#### ResourceType:uddbnode

|参数|描述信息|单位|
|:---|:---|:---|
| **CoreFailure**|核心管理功能失效|次|
| **MemUsage**|内存使用率|%|
|**RWProxyCpuUtil**|CPU使用率|%|
|**SlaveDelay**|从库同步延迟|s|
|**QPS**|QPS|次/s|
|**CPUCoreUsed**|CPU使用量(核数)|个|
|**ConnectionCount**|连接数|个|
|**MemUsage**|内存使用率|%|
|**DeleteQPS**|删除QPS|次/s|
|**DumpFailure**|DB备份导出失败||
|**ExpensiveQuery**|慢查询|个|
|**InsertQPS**|插入QPS|次/s|
|**SandboxMemory**|DB系统总内存|MB|
|**SynchronizationError**|主从同步|个|
|**SandboxCache**|DB系统总缓存|MB|
|**BackupFailed**|备份失败|次|
|**ServiceAvailability**|DB可用性错误||
|**PingErrorCount**|db连通情况|个|
|**TPS**|每秒事务数|次/s|
|**ReplaceQPS**|ReplaceQPS|次/s|
|**ConnectionMaxFlag**|连接数是否打满||
|**DiskUsage**|磁盘使用率|%|
|**IOOps|IO平均读写次数**|次/s|
|**RWProxyQPS**|qps|次/s|
|**CPUUtilization**|CPU使用率|%|
|**IO**|IO平均读写字节数|Bps|
|**RWProxyConnCount**|连接数|个/min|
|**SelectQPS**|查询QPS|次/s|
|**MemSize**|内存大小|MB|
|**AbReboot**|异常重启|次|
|**CPUUtilization**|CPU使用率|%|
|**RWProxyMemUtil**|内存使用率|%|
|**UpdateQPS**|更新QPS|次/s|
|**ConnectionCount|**连接数|个|

#### ResourceType:udw

|参数|描述信息|单位|
|:---|:---|:---|
|**SegmentDown**|udw异常segment|个|
|**UdwQPS**|每秒查询率|次/s|
|**UdwDbConnections**|数据库连接数|个|
|**UdwDiskUsage**|集群磁盘容量使用率|%|
|**ServiceStatus**|udw服务状态||

#### ResourceType:anycasteip

|参数|描述信息|单位|
|:---|:---|:---|
|**NetworkIn**|网络入口|bps|
|**NetworkOut**|网络出口|bps|
|**NetworkInUsage**|入口带宽使用率|%|
|**NetworkOutUsage**|出口带宽使用率|%|

#### ResourceType:udisk_sys

|参数|描述信息|单位|
|:---|:---|:---|
|**BytesWrite**|BYTEPSWRITE|Bps|
|**IOPSRead**|IOPSREAD|次/s|
|**IOPSWrite**|IOPSWRITE|次/s|
|**BytesRead**|BYTEPSREAD|Bps|

#### ResourceType:udset_uhost

|参数|描述信息|单位|
|:---|:---|:---|
|**IOWrite**|磁盘写流量|Bps|
|**BlockProcessCount**|阻塞进程数目|个|
|**DiskReadOps**|磁盘读次数|次/s|
|**ReadonlyDiskCount**|云主机只读磁盘个数|个|
|**DiskWriteOps**|磁盘写次数|次/s|
|**ProcessCount**|进程总数|个|
|**NICIn**|网卡入带宽|bps|
|**TcpConnectCount**|TCP连接数|个|
|**NICOut**|网卡出带宽|bps|
|**LoadAvg1m**|loadavg1分钟||
|**NetPacketIn**|网卡入包量|个/s|
|**LoadAvg5m**|loadavg5分钟||
|**NetPacketOut**|网卡出包量|个/s|
|**LoadAvg15m**|loadavg15分钟||
|**MemUsage**|内存使用率|%|
|**DataSpaceUsage**|数据盘磁盘空间使用率|%|
|**CPUUtilization**|CPU使用率|%|
|**RootSpaceUsage**|系统盘磁盘空间使用率|%|
|**IORead**|磁盘读流量|Bps|
|**RunnableProcessCount**|运行进程数目|个|

#### ResourceType:uddbmd

|参数|描述信息|单位|
|:---|:---|:---|
|**CPUUtilization**|CPU使用率|%|
|**MemUsage**|内存使用率|%|
|**ConnectionCount**|连接数|个|

#### ResourceType:tidb

|参数|描述信息|单位|
|:---|:---|:---|
|**tidb_slow_query_duration_95**|慢查询执行时间95值|s|
|**tikv_cop_wait_duration_avg**|tikv coprocessor 平均等待时间|us|
|**tidb_slow_query_duration_80**|慢查询执行时间80值|s|
|**tikv_cop_handle_time_avg_select**|tikv coprocessor 平均处理时间select|ms|
|**tidb_storage_size**|tidb实例存储量|Byte|
|**tidb_parse_duration_99**|sql解析时间99值|ms|
|**tikv_cop_handle_time_avg_index**|tikv coprocessor 平均处理时间index|ms|
|**tidb_qps**|tidb实例qps|次/s|
|**tidb_parse_duration_95**|sql解析时间95值|ms|
|**tikv_block_cache_hit**|tikv块缓存命中率|%|
|**tidb_query_duration_99**|sql 执行时间99值|ms|
|**tidb_tps**|tidb实例tps|次/s|
|**tidb_parse_duration_80**|sql解析时间80值|ms|
|**binlog_execute_time**|binglog写从库耗时|ms|
|**tidb_query_duration_95**|sql 执行时间95值|ms|
|**tidb_mem_usage**|tidb实例内存使用量|Byte|
|**tiflash_mem_usage**|Tidb集群中TiFlash节点的内存使用量|Byte|
|**tikv_apply_log_duration_99**|tikv raftstore apply log 时间99值|us|
|**write_binlog_latency_99**|binglog写延时99值|ms|
|**tidb_query_duration_80**|sql 执行时间80值|ms|
|**tiflash_storage_size**|Tidb集群中TiFlash节点的磁盘使用量|Byte|
|**tikv_apply_log_duration_95**|tikv raftstore apply log 时间95值|us|
|**write_binlog_latency_95**|binglog写延时95值|ms|
|**tidb_tnx_duration_99**|事务执行时间99值|ms|
|**tikv_apply_log_duration_avg**|tikv raftstore apply log 时间平均值|us|
|**pump_storage_size**|tidb实例pump存储容量|Byte|
|**write_binlog_qps**|写binglog qps|次/s|
|**tidb_tnx_duration_95**|事务执行时间95值|ms|
|**tikv_append_log_duration_99**|tikv raftstore append log 时间99值|us|
|**drainer_mem_usage**|tidb实例drainer内存使用量|Byte|
|**tidb_tnx_duration_80**|事务执行时间80值|ms|
|**tikv_append_log_duration_95**|tikv raftstore append log 时间95值|us|
|**pump_mem_usage**|tidb实例pump内存使用量|Byte|
|**tidb_slow_query_duration_99**|慢查询执行时间99值|s|
|**tikv_append_log_duration_avg|tikv raftstore append log 时间平均值**|us|

#### ResourceType:uddb

|参数|描述信息|单位|
|:---|:---|:---|
| **SlowSQL**|慢SQL|次|
| **ErrorSQL**|错误SQL|次|
| **QPS**|QPS|个/s|
| **CPUUtilization**|CPU利用率|%|
| **ConnectionCount** |连接数|个|
| **MemUsage** |内存利用率|%|


#### ResourceType:docker_node

|参数|描述信息|单位|
|:---|:---|:---|
| **NetPacketIn** |网卡入包量|个/s|
| **LoadAvg5m** |loadavg5分钟||
| **NetPacketOut** |网卡出包量|个/s|
| **LoadAvg15m** |loadavg15分钟||
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **IORead** |磁盘读流量|Bps|
| **RunnableProcessCount** |运行进程数目|个|
| **IOWrite|磁盘写流量** |Bps|
| **BlockProcessCount** |阻塞进程数目|个|
| **DiskReadOps** |磁盘读次数|次/s|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **DiskWriteOps** |磁盘写次数|次/s|
| **ProcessCount** |进程总数|个|
| **NICIn** |网卡入带宽|bps|
| **TcpConnectCount** |TCP连接数|个|
| **NICOut** |网卡出带宽|bps|
| **LoadAvg1m** |loadavg1分钟||

#### ResourceType:vpntunnel

|参数|描述信息|单位|
|:---|:---|:---|
| **SAOut** |隧道出流量|bps|
| **SAIn** |隧道入流量|bps|
| **VPNTunnelState** |vpngw隧道状态|bool|

#### ResourceType:hybridcloud_lan

|参数|描述信息|单位|
|:---|:---|:---|
| **BandToPublicCloud** |托管云向公有云的流量|bps|
| **BandToHybridCloud** |公有云向托管云的流量|bps|

#### ResourceType:uaiservice

|参数|描述信息|单位|
|:---|:---|:---|
| **MaxReqTime** |最大请求时间|ms|
| **ReqFailCnt** |请求失败数|次|
| **MinReqTime** |最小请求时间|ms|
| **RtCode3xxCnt** |3xx状态码个数|次|
| **AvgReqTime** |平均请求时间|ms|
| **RtCode4xxCnt** |4xx状态码个数|次|
| **RtCode5xxCnt** |5xx状态码个数|次|
| **EightyReqTime** |80%请求耗时|ms|
| **EightyFiveReqTime** |85%请求耗时|ms|
| **NinetyReqTime** |90%请求耗时|ms|
| **TotalReqCnt** |请求总数|次|
| **NinetyFiveReqTime** |95%请求耗时|ms|
| **ReqSuccCnt** |请求成功数|次|

#### ResourceType:ukv

|参数|描述信息|单位|
|:---|:---|:---|
| **UKVInstanceUsage** |使用量|KB|
| **UKVInstanceUsageRate** |使用率|%|
| **UKVInstanceRecordCount** |记录数|个|
| **UKVInstanceGetQPS** |GetQPS|次/s|
| **UKVInstanceSetQPS** |SetQPS|次/s|
| **UKVInstanceTotalQPS** |TotalQPS|次/s|
| **UKVInstanceGetHit** |Get命中数|次|
| **UKVInstanceGetHitRate** |Get命中率|%|
| **UKVInstanceConnCount** |连接数|个|

#### ResourceType:udisk_rssd

|参数|描述信息|单位|
|:---|:---|:---|
| **BytesWrite** |BYTEPSWRITE|Bps|
| **IOPSRead** |IOPSREAD|次/s|
| **IOPSWrite** |IOPSWRITE|次/s|
| **BytesRead** |BYTEPSREAD|Bps|

#### ResourceType:epc

|参数|描述信息|单位|
|:---|:---|:---|
| **LoadAvg15m** |loadavg15分钟||
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **IORead** |磁盘读流量|Bps|
| **RunnableProcessCount** |运行进程数目|个|
| **IOWrite** |磁盘写流量|Bps|
| **BlockProcessCount** |阻塞进程数目|个|
| **DiskReadOps** |磁盘读次数|次/s|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **DiskWriteOps** |磁盘写次数|次/s|
| **ProcessCount** |进程总数|个|
| **NICIn** |网卡入带宽|bps|
| **TcpConnectCount** |TCP连接数|个|
| **NICOut** |网卡出带宽|bps|
| **LoadAvg1m** |loadavg1分钟||
| **NetPacketIn** |网卡入包量|个/s|
| **LoadAvg5m** |loadavg5分钟||
| **NetPacketOut** |网卡出包量|个/s|

#### ResourceType:hybridcloud_port_sum

|参数|描述信息|单位|
|:---|:---|:---|
| **BandIn** |混合云端口入带宽|bps|
| **BandOut** |混合云端口出带宽|bps|
| **BandIn** |混合云端口入带宽|bps|
| **BandOut** |混合云端口出带宽|bps|

#### ResourceType:dbaudit

|参数|描述信息|单位|
|:---|:---|:---|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **IORead** |磁盘读流量|Bps|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
#### ResourceType:urocketmq

|参数|描述信息|单位|
|:---|:---|:---|
| **rocketmq_group_get_latency_by_storetime** |消费延迟|ms|
| **rocketmq_producer_tps** |每秒生产消息个数|个/s|
| **rocketmq_producer_message_size** |每秒生产数据|Bps|
| **rocketmq_consumer_tps** |每秒消费消息个数|个/s|
| **rocketmq_consumer_message_size** |每秒消费数据|Bps|
| **rocketmq_group_diff** |消息堆积个数|个|
#### ResourceType:uaicensor

|参数|描述信息|单位|
|:---|:---|:---|
| **ImageScanFailReqCnt** |UAI图片审核接口调用失败次数|次|
| **TupuPornLeftCnt** |UAI算法平台图普色情识别流量包剩余次数|次|
| **VideoAsyncScanTotalReqCnt** |UAI视频异步审核接口调用总次数|次|
| **TupuPoliticsLeftCnt** |UAI算法平台图普敏感人物识别流量包剩余次数|次|
| **VideoAsyncScanSuccReqCnt** |UAI视频异步审核接口调用成功次数|次|
| **TupuTerrorLeftCnt** |UAI算法平台图普暴恐识别流量包剩余次数|次|
| **VideoAsyncScanFailReqCnt** |UAI视频异步审核接口调用失败次数|次|
| **PornImageCnt** |UAI内容审核涉黄图片数|个|
| **UCloudPornLeftCnt** |UAI算法平台UCloud色情识别流量包剩余次数|次|
| **VideoSyncScanTotalReqCnt** |UAI视频同步审核接口调用总次数|次|
| **CheckImageCnt** |UAI内容审核可疑图片数|个|
| **UCloudMaskLeftCnt** |UAI算法平台UCloud口罩检测流量包剩余次数|次|
| **VideoSyncScanSuccReqCnt** |UAI视频同步审核接口调用成功次数|次|
| **ImageScanAvgReqTime** |UAI图片审核接口平均耗时|ms|
| **VideoSyncScanFailReqCnt** |UAI视频同步审核接口调用失败次数|次|
| **VideoAsyncScanAvgReqTime** |UAI视频异步审核接口平均耗时|ms|
| **NormalImageCnt** |UAI内容审核正常图片数|个|
| **VideoSyncScanAvgReqTime** |UAI视频同步审核接口平均耗时|ms|
| **ImageScanTotalReqCnt** |UAI图片审核接口调用总次数|次|
| **ImageScanSuccReqCnt** |UAI图片审核接口调用成功次数|次|

#### ResourceType:ugc

|参数|描述信息|单位|
|:---|:---|:---|
| **FailedRequests** |UGC请求失败数|个/min|
| **RequestCost** |UGC请求平均耗时|ms|
#### ResourceType:upath

|参数|描述信息|单位|
|:---|:---|:---|
| **UpathNetworkIn** |全球动态加速upath入带宽|bps|
| **UpathNetworkOut** |全球动态加速upath出带宽|bps|
| **UpathNetworkInUsage** |全球动态加速upath入带宽使用率|%|
| **UpathNetworkOutUsage** |全球动态加速upath出带宽使用率|%|
#### ResourceType:udns

|参数|描述信息|单位|
|:---|:---|:---|
| **UDNSZoneQps** |UDNS每秒查询次数|个/s|

#### ResourceType:udset

|参数|描述信息|单位|
|:---|:---|:---|
| **IORead** |读吞吐量|MB/s|
| **IOWrite** |写吞吐量|MB/s|
| **CPUUtilization** |CPU使用率|%|
| **NICIn** |流入流量|Mb|
| **NICOut** |流出流量|Mb|
| **NetPacketIn** |流入包量|个/s|
| **NetPacketOut** |流出包量|个/s|
| **DiskReadOps** |读iops|次/s|
| **DiskWriteOps** |写iops|次/s|

#### ResourceType:ugaa

|参数|描述信息|单位|
|:---|:---|:---|
| **SourceOutRetransmitRate** |全球加速出重传率|%|
| **SourceBandIn** |全球加速源入带宽|bps|
| **SourceBandOut** |全球加速源出带宽|bps|
| **SourceBandInUsage** |全球加速源入带宽使用率|%|
| **SourceBandOutUsage** |全球加速源出带宽使用率|%|
| **SourceTcpConnectNum** |全球加速tcp连接数|个|
| **SourceTcpDelay** |全球加速tcp延时|ms|
| **SourceInRetransmitRate** |全球加速入重传率|%|

#### ResourceType:fortress

|参数|描述信息|单位|
|:---|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **IORead|磁盘读流量** |Bps|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn|** 网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|

#### ResourceType:ufs

|参数|描述信息|单位|
|:---|:---|:---|
| **FsRemainingSize** |文件系统剩余容量|GB|
| **FsUsageRate** |文件系统容量使用率|%|
| **FsStatSize** |文件系统的size字节数|Byte|
| **FsStatFiles** |文件系统的文件个数|个|

#### ResourceType:ues_node

|参数|描述信息|单位|
|:---|:---|:---|
| **DiskUsage** |节点磁盘使用率|%|
| **QueryLatency** |查询延迟|ms/次|
| **DiskIORead** |节点磁盘读吞吐量|Bps|
| **IndexCount** |写入次数|次/s|
| **DiskIOWrite** |节点磁盘写吞吐量|Bps|
| **IndexLatency** |写入延迟|ms/次|
| **NetworkIn** |节点网络带宽入量|Bps|
| **RejectQuery** |查询拒绝率|%|
| **NetworkOut** |节点网络带宽出量|Bps|
| **RejectWrite** |写入拒绝率|%|
| **DiskReadCount** |节点磁盘读次数|次|
| **DiskWriteCount** |节点磁盘写次数|次|
| **NetInPackets** |节点网卡入包量|个/s|
| **NetOutPackets** |节点网卡出包量|个/s|
| **CpuUsage** |节点cpu利用率|%|
| **MemoryUsage** |节点内存利用率|%|
| **QueryCount** |查询次数|次/s|

#### ResourceType:uclickhousenode

|参数|描述信息|单位|
|:---|:---|:---|
| **UclickhouseDBConnection** |数据库连接数|个|
| **UclickhouseIoOut** |流量写出|Mbps|
| **UclickhouseDBInsertSize** |每秒写入大小|Kbps|
| **UclickhouseDBSelectSize** |select查询数|个/s|
| **UclickhouseInsertTime** |插入总时长|ms|
| **UclickhouseSelectTime** |查询总时长|ms|
| **UclickhouseCPUUsage** |cpu使用率|%|
| **UclickhouseMemoryUsage** |内存利用率|%|
| **UclickhouseDiskIopsRead** |读iops|KBps|
| **UclickhouseDiskUsage** |磁盘使用率|%|
| **UclickhouseDiskIopsWrite** |写iops|KBps|
| **UclickhouseIoPut** |流量写入|Mbps|


#### ResourceType:uddbac

|参数|描述信息|单位|
|:---|:---|:---|
| **SlowSQL** |慢查询|个/s|
| **ErrorSQL** |错误SQL|个/s|
| **QPS** |QPS|次/s|
| **ConnectionCount** |连接数|个|
| **CPUUtilization** |CPU利用率|%|
| **MemUtilization** |内存利用率|%|

#### ResourceType:hybridcloud_port

|参数|描述信息|单位|
|:---|:---|:---|
| **BandOut** |混合云端口出带宽|bps|
| **BandIn** |混合云端口入带宽|bps|

#### ResourceType:ues

|参数|描述信息|单位|
|:---|:---|:---|
| **TotalDiskUsage** |集群磁盘容量使用率|%|
| **ClusterHealthStatus** |集群健康状态||

#### ResourceType:utsdb

|参数|描述信息|单位|
|:---|:---|:---|
| **UInfluxdbMemoryUsage** |UInfluxdb内存使用率|%|
| **UInfluxdbQps** |UInfluxdb QPS|次/s|
| **UInfluxdbDiskUsage** |UInfluxdb磁盘使用量|GB|
| **UInfluxdbCpuUsage** |UInfluxdb Cpu使用率|%|


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
