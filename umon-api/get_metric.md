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
###### 云主机

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **RunnableProcessCount** |运行进程数目|个|
| **BlockProcessCount** |阻塞进程数目|个|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **ProcessCount** |进程总数|个|
| **TcpConnectCount** |TCP连接数|个|
| **LoadAvg1m** |loadavg1分钟||
| **LoadAvg5m** |loadavg5分钟||
| **LoadAvg15m** |loadavg15分钟||
| **MemoryFreeSpace** |空闲内存量|MB|
| **MemoryActualusedSpace** |已用内存量|MB|
| **MemoryAvailableSpace** |可用内存量|MB|





#### ResourceType:udb
###### 云数据库

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **DiskUsage** |磁盘使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **MemSize** |内存大小|MB|
| **ConnectionCount** |连接数|个|
| **QPS** |QPS|次/s|
| **DeleteQPS** |删除QPS|次/s|
| **InsertQPS** |插入QPS|次/s|
| **SelectQPS** |查询QPS|次/s|
| **UpdateQPS** |更新QPS|次/s|
| **SlaveDelay** |从库同步延迟|s|
| **MemUsage** |内存使用率|%|
| **ExpensiveQuery** |慢查询|个|
| **SynchronizationError** |主从同步|个|
| **BackupFailed** |备份失败|次|
| **PingErrorCount** |db连通情况|个|
| **ReplaceQPS** |ReplaceQPS|次/s|
| **IOOps** |IO平均读写次数|次/s|
| **IO** |IO平均读写字节数|Bps|
| **AbReboot** |异常重启|次|
| **CoreFailure** |核心管理功能失效|次|
| **CPUCoreUsed** |CPU使用量(核数)|个|
| **DumpFailure** |DB备份导出失败||
| **IDHASlaveError** |高可用双主同步异常||
| **SandboxMemory** |DB系统总内存|MB|
| **SandboxCache** |DB系统总缓存|MB|
| **ServiceAvailability** |DB可用性错误||
| **TPS** |每秒事务数|次/s|
| **ConnectionMaxFlag** |连接数是否打满||
| **HAStandyDBDiskUsage** |高可用备主磁盘使用率|%|
| **RWProxyQPS** |qps|次/s|
| **RWProxyConnCount** |连接数|个/min|
| **RWProxyMemUtil** |内存使用率|%|
| **RWProxyCpuUtil** |CPU使用率|%|
| **HAHealthState** |高可用状态异常||
| **HASyncDelay** |高可用主备数据同步延时|s|
| **ActiveMemoryRatio** |活跃内存占比|%|
| **IOAwait** |磁盘的IO响应时间|ms|
| **MongoDBActiveClientReaders** |MongoDB正在读的客户端数|个|
| **MongoDBActiveClientWriters** |MongoDB正在写的客户端数|个|
| **MongoDBInsertOPCountsTotal** |MongoDB累计插入操作数|个|
| **MongoDBQueryOPCountsTotal** |MongoDB累计查询操作数|个|
| **MongoDBUpdateOPCountsTotal** |MongoDB累计更新操作数|个|
| **MongoDBDeleteOPCountsTotal** |MongoDB累计删除操作数|个|
| **MongoDBGetMoreOPCountsTotal** |MongoDB累计getMore操作数|个|
| **MongoDBCommandOPCountsTotal** |MongoDB累计执行管控命令操作数|个|
| **MongoDBCurrentQueueTotal** |MongoDB读写等待队列总长度|个|
| **MongoDBActiveConns** |MongoDB活跃连接数|个|
| **MongoDBWTCacheReadIntoSizeTotal** |MongoDB WT缓存读入累计数据量|Byte|
| **MongoDBWTCacheWrittenFromSizeTotal** |MongoDB WT缓存落盘累计数据量|Byte|
| **MongoDBWTMaxSize** |MongoDB WT缓存总大小|Byte|
| **MongoDBWTCacheUsage** |MongoDB WT缓存使用率|%|
| **MongoDBWTCacheDirtyUsage** |MongoDB WT缓存脏页占用率|%|
| **MongoDBWTReadFromDiskSizeTotal** |MongoDB WT磁盘读取累计数据量|Byte|
| **MongoDBWTWrittenIntoDiskSizeTotal** |MongoDB WT磁盘写入累计数据量|Byte|
| **MongoDBCurrentQueueReaders** |MongoDB当前等待读队列长度|个|
| **MongoDBCurrentQueueWriters** |MongoDB当前等待写队列长度|个|
| **MySQLBytesReceived** |MySQL接收总数据量|Byte|
| **MySQLBytesReceivedRate** |MySQL每秒接收数据量|bytes/s|
| **MySQLBytesSent** |MySQL发送总数据量|Byte|
| **MySQLBytesSentRate** |MySQL每秒发送数据量|bytes/s|
| **IOUtilizationRatio** |IO利用率|%|
| **IOAverageQueueSize** |IO等待长度||
| **HaStandbyCPUUtilization** |高可用备库CPU使用率|%|
| **HaStandbyIOAverageQueueSize** |高可用备库IO等待长度|个/s|
| **HaStandbyMemUsage** |高可用备库内存使用率|%|
| **HaStandbyIOAwait** |高可用备库磁盘IO响应时间|ms|
| **HaStandbyIOUtilizationRatio** |高可用备库IO利用率|%|
| **HAFailover** |容灾记录|次|
| **HAStandbyOOM** |高可用备库OOM|次|
| **OOM** |OOM|次|





#### ResourceType:eip
###### 弹性IP

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **NetworkIn** |网络入口|bps|
| **NetworkOut** |网络出口|bps|
| **FlowIn** |外网入流量|Byte|
| **FlowOut** |外网出流量|Byte|
| **NetworkInUsage** |入口带宽使用率|%|
| **NetworkOutUsage** |出口带宽使用率|%|
| **EIPIdTopOutBW** |EIPId出向峰值带宽|bps|
| **EIPIdTopInBW** |EIPId入向峰值带宽|bps|
| **EIPIdOutPPS** |eipId出向发包速率|个/s|
| **EIPIdInPPS** |eipId入向发包速率|个/s|
| **EIPIdOutDropPPS** |eipId出向丢包速率|个/s|
| **EIPIdInDropPPS** |eipId入向丢包速率|个/s|
| **EIPIdOutDropRate** |eipId出向丢包百分比|%|
| **EIPIdInDropRate** |eipId入向丢包百分比|%|





#### ResourceType:sharebandwidth
###### 共享带宽

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **BandOut** |出口带宽|bps|
| **BandIn** |入口带宽|bps|
| **NetworkOutUsage** |出口带宽使用率|%|
| **NetworkInUsage** |入口带宽使用率|%|





#### ResourceType:hybridcloud_port_sum
###### 混合云外网带宽

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **BandIn** |流入带宽|bps|
| **BandOut** |流出带宽|bps|





#### ResourceType:uredis
###### 主备版redis

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **InstanceUsage** |使用量|KB|
| **URedisInstanceConnCount** |连接数|个|
| **QPS** |总QPS|次/s|
| **URedisExpiredKeys** |过期key|个|
| **InstanceKey** |实例Key数量|个|
| **InstanceGetHit** |实例命中次数|个|
| **InstanceGetHitRate** |实例命中率|%|
| **InstanceTotalGetQPS** |总GetQPS|次/s|
| **InstanceTotalSetQPS** |总SetQPS|次/s|
| **InstanceListQPS** |LlistQPS|次/s|
| **InstanceStringQPS** |StringQPS|次/s|
| **InstanceHashQPS** |HashQPS|次/s|
| **InstanceSetQPS** |SetQPS|次/s|
| **InstanceZsetQPS** |ZsetQPS|次/s|
| **InstanceHyperloglogQPS** |实例hyperloglogQPS|次/s|
| **InstancePubsubQPS** |实例pubsubQPS|次/s|
| **InstanceTransactionQPS** |实例transactionQPS|次/s|
| **RedisSinglenodeMaxload** |Redis负载|%|
| **NICIn** |入带宽|Bps|
| **NICOut** |出带宽|Bps|
| **Usage** |内存使用量|%|
| **RedisAvgCPULoad** |Redis平均CPU负载|%|
| **URedisFragmentationRatio** |主备redis内存碎片率|%|
| **URedisSlaveSyncState** |URedis主从同步状态|bool|
| **URedisCurrentAofSize** |当前aof文件大小|KB|
| **ConnectCountUsage** |连接数使用率|%|
| **URedisKeyEvicted** |历史累计逐出key总数|个|
| **URedisMaxRt** |最大请求延迟|us|
| **URedisAvgRt** |平均请求延迟|us|
| **URedisUsedMemoryDataset** |数据占用内存|KB|
| **URedisBlockClients** |等待阻塞命令的连接|个|
| **URedisMissPerSec** |每秒miss率|%|
| **SlaveClientOutputBufSize** |从库客户端输出buf大小|KB|
| **NormalClientOutputBufSize** |普通客户端输出buf大小|KB|





#### ResourceType:uhadoop
###### 托管Hadoop集群

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **HdfsTotal** |hdfs总容量|GB|
| **HdfsUsed** |hdfs当前所用容量|GB|
| **HdfsAvailable** |hdf当前可用容量|GB|
| **AppsSubmitted** |yarn上app提交总数|个|
| **AppsCompleted** |yarn上app已完成总数|个|
| **AppsPending** |yarn上等待中的app数量|个|
| **AppsRunning** |yarn上正在运行中的app数量|个|
| **AppsFailed** |yarn上失败app数量|个|
| **AppsKilled** |yarn上终止app数量|个|
| **AvailableMem** |yarn上未分配内存|MB|
| **AllocatedMem** |yarn上已分配内存|MB|
| **TotalMem** |yarn上总配置内存|MB|
| **AvailableVirtualCores** |yarn上未分配core数|个|
| **AllocatedVirtualCores** |yarn上已分配core数|个|
| **TotalVirtualCores** |yarn上总配置core数|个|
| **ContainersAllocated** |yarn上已分配的container|个|
| **ContainersPending** |yarn上等待状态的container|个|
| **HdfsUsage** |hdfs使用百分比|%|
| **MemoryUsage** |yarn上已分配内存百分比|%|
| **UnhealthyNodeManager** |不正常的NodeManager|个|
| **LostNodeManager** |丢失的NodeManager|个|
| **DeadDataNode** |集群失效的数据节点|个|
| **LiveNodeCount** |探活的节点个数|个|
| **NameNodeInActiveCount** |NameNode是active的个数|个|
| **NameNodeInSafemodeCount** |NameNode处于safemode的个数|个|
| **ActiveNameNodeInSafemodCount** |active的NameNode处于safemode的个数|个|
| **ActiveResourceManagerNum** |Active状态的resourceManage数量|个|
| **AbnomralJournalNodeNum** |不正常的journalNode数量|个|
| **AbnomralRegionServerNum** |不正常的regionServer数量|个|
| **AbnomralDataNodeNum** |不正常的datanode数量|个|
| **AbnormalYarnNodeNum** |不正常的yarnnodeNum|个|
| **AbnomralNameNodeNum** |不正常的nameNode数量|个|





#### ResourceType:uhadoop_host
###### 托管Hadoop集群节点

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **RunnableProcessCount** |运行进程数目|个|
| **BlockProcessCount** |阻塞进程数目|个|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **ProcessCount** |进程总数|个|
| **TcpConnectCount** |TCP连接数|个|
| **LoadAvg1m** |loadavg1分钟||
| **LoadAvg5m** |loadavg5分钟||
| **LoadAvg15m** |loadavg15分钟||
| **SysDiskIOUtil** |系统盘磁盘io使用率|%|
| **DataDiskIOUtil** |数据盘磁盘io使用率|%|
| **LiveNodeCount** |探活的节点个数|个|
| **AgentHealth** |agent健康状态||





#### ResourceType:ukafka
###### Kafka消息队列

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **MessagesInPerSec** |每秒流入消息个数|个/s|
| **BytesInPerSec** |每秒流入数据|Bps|
| **BytesOutPerSec** |每秒流出数据|Bps|
| **FailedFetchRequestsPerSec** |消费者失败请求|次/s|
| **FailedProduceRequestsPerSec** |生产者失败请求|次/s|
| **BytesRejectedPerSec** |Broker拒绝的消息|Bps|
| **ZkNumAliveConnections** |zk当前活跃连接数|个|
| **ZkMaxRequestLatency** |zk最大请求延时   |ms|
| **ZkAvgRequestLatency** |zk平均请求延时|ms|
| **ZkMinRequestLatency** |zk最小请求延时|ms|
| **ZkPacketsSent** |zk发送响应数|个|
| **ZkPacketsReceived** |zk接收响应数|个|
| **ZkOutstandingRequests** |zk待处理连接数|个|
| **ZkWatchCount** |watches的数量|个|
| **ZkNodeCount** |znodes的数量|个|
| **LeaderFeq** |leader选举频率|ms|
| **ControllerCount** |controller存活数目|个|
| **ProducerListCount** |producer队列中排队请求数|个|
| **ProducerTimeout** |producer请求响应时间|ms|
| **ProducerQPS** |producerQPS|次/s|
| **ConsumerListCount** |consumer队列中排队请求数|个|
| **ConsumerTimeout** |consumer请求响应时间|ms|
| **ConsumerQPS** |consumerQPS|次/s|
| **kafkaLiveBrokerCount** |Kafka存活节点个数|个|





#### ResourceType:ukafka_host
###### Kafka消息队列节点

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **MessagesInPerSec** |每秒流入消息个数|个/s|
| **BytesInPerSec** |每秒流入数据|Bps|
| **BytesOutPerSec** |每秒流出数据|Bps|
| **ReplicaMaxLag** |Follower落后Leader的最大消息量|个|
| **PartitionCount** |分布在该节点上的分区总数|个|
| **LeaderCount** |分布在该节点上的leader分区总数|个|
| **UnderReplicatedPartitions** |未复制的分区总数|个|
| **IsrExpandsPerSec** |ISR扩大速率|个/s|
| **IsrShrinksPerSec** |ISR收缩速率|个/s|
| **ActiveControllerCount** |管理节点个数|个|
| **OfflinePartitionsCount** |离线分区总数|个|
| **FailedFetchRequestsPerSec** |消费者失败请求|次/s|
| **FailedProduceRequestsPerSec** |生产者失败请求|次/s|
| **BytesRejectedPerSec** |Broker拒绝的消息|Bps|
| **ZkNumAliveConnections** |zk当前活跃连接数|个|
| **ZkMaxRequestLatency** |zk最大请求延时   |ms|
| **ZkAvgRequestLatency** |zk平均请求延时|ms|
| **ZkMinRequestLatency** |zk最小请求延时|ms|
| **ZkPacketsSent** |zk发送响应数|个|
| **ZkPacketsReceived** |zk接收响应数|个|
| **ZkOutstandingRequests** |zk待处理连接数|个|
| **ZkWatchCount** |watches的数量|个|
| **ZkNodeCount** |znodes的数量|个|
| **ProducerListCount** |producer队列中排队请求数|个|
| **ProducerTimeout** |producer请求响应时间|ms|
| **ProducerQPS** |producerQPS|次/s|
| **ConsumerListCount** |consumer队列中排队请求数|个|
| **ConsumerTimeout** |consumer请求响应时间|ms|
| **ConsumerQPS** |consumerQPS|次/s|
| **kafkaLiveBrokerCount** |Kafka存活节点个数|个|





#### ResourceType:phost
###### 物理云主机

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **RootSpaceUsage** |系统盘使用率|%|
| **DataSpaceUsage** |数据盘使用率|%|
| **LoadAvg1m** |1分钟负载统计||
| **LoadAvg5m** |5分钟负载统计||
| **LoadAvg15m** |15分钟负载统计||
| **MemUsage** |内存使用率|%|
| **MemFree** |空闲内存|Kb|
| **TcpConnectCount** |tcp连接数|个|
| **ProcessCount** |进程数|个|
| **ReadonlyDiskCount** |只读磁盘个数|个|
| **RunnableProcessCount** |运行进程数|个|
| **BlockProcessCount** |阻塞进程数|个|
| **CPUUtilization** |cpu使用率|%|
| **IORead** |磁盘读吞吐|Bps|
| **IOWrite** |磁盘写吞吐|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **UpmDiskHealthCheck** |物理云磁盘健康状态检查||
| **GPUTemp** |GPU最高温度|℃|
| **UphostMemoryEccError** |内存ECC报错|个|
| **UphostRoDiskCount** |磁盘异常(ro)个数|个|





#### ResourceType:fortress
###### 堡垒机

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|





#### ResourceType:udset
###### 私有专区资源池

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **NICIn** |流入流量|Mb|
| **NICOut** |流出流量|Mb|
| **NetPacketIn** |流入包量|个/s|
| **NetPacketOut** |流出包量|个/s|
| **DiskReadOps** |读iops|次/s|
| **DiskWriteOps** |写iops|次/s|
| **IORead** |读吞吐量|MB/s|
| **IOWrite** |写吞吐量|MB/s|





#### ResourceType:udset_uhost
###### 私有专区主机

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **RunnableProcessCount** |运行进程数目|个|
| **BlockProcessCount** |阻塞进程数目|个|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **ProcessCount** |进程总数|个|
| **TcpConnectCount** |TCP连接数|个|
| **LoadAvg1m** |loadavg1分钟||
| **LoadAvg5m** |loadavg5分钟||
| **LoadAvg15m** |loadavg15分钟||





#### ResourceType:ues
###### ES集群

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **TotalDiskUsage** |集群磁盘容量使用率|%|
| **ClusterHealthStatus** |集群健康状态||





#### ResourceType:ues_node
###### ES集群节点

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CpuUsage** |节点cpu利用率|%|
| **MemoryUsage** |节点内存利用率|%|
| **DiskUsage** |节点磁盘使用率|%|
| **DiskIORead** |节点磁盘读吞吐量|Bps|
| **DiskIOWrite** |节点磁盘写吞吐量|Bps|
| **NetworkIn** |节点网络带宽入量|Bps|
| **NetworkOut** |节点网络带宽出量|Bps|
| **DiskReadCount** |节点磁盘读次数|次|
| **DiskWriteCount** |节点磁盘写次数|次|
| **NetInPackets** |节点网卡入包量|个/s|
| **NetOutPackets** |节点网卡出包量|个/s|
| **QueryCount** |查询次数|次/s|
| **QueryLatency** |查询延迟|ms/次|
| **IndexCount** |写入次数|次/s|
| **IndexLatency** |写入延迟|ms/次|
| **RejectQuery** |查询拒绝率|%|
| **RejectWrite** |写入拒绝率|%|





#### ResourceType:ufs
###### 文件存储

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **FsStatSize** |文件系统的size字节数|Byte|
| **FsStatFiles** |文件系统的文件个数|个|
| **ReadCount** |read请求数|次|
| **WriteCount** |write请求数|次|
| **WriteSize** |nfs协议write请求流量|Byte|
| **ReadSize** |nfs协议read请求流量|Byte|
| **ReadLatency** |read延迟90百分位|ms|
| **WriteLatency** |write延迟90百分位|ms|
| **FsRemainingSize** |文件系统剩余容量|GB|
| **FsUsageRate** |文件系统容量使用率|%|





#### ResourceType:ucdn
###### 云分发

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **bandwidth** |带宽|bps|
| **flow** |流量|GB|
| **Returnsourcebandwidth** |回源带宽|bps|
| **Hitrate** |命中率|%|
| **Returncode4xxratio** |返回码4xx占比|%|
| **Returncode5xxratio** |返回码5xx占比|%|
| **ReturnToSource5xxStatusCode** |回源5xx状态码|%|
| **ReturnToSource4xxStatusCode** |回源4xx状态码|%|
| **UcdnTotalBandwidth** |CDN总带宽|bps|





#### ResourceType:udpn
###### 高速通道

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **BandOut** |专线出向带宽|bps|
| **BandOutMax** |专线出向带宽峰值|bps|
| **BandOutUsage** |带宽使用率|%|
| **BandOutMaxUsage** |峰值带宽使用率|%|





#### ResourceType:umemcache
###### 单机版memcache

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **InstanceUsage** |已使用内存|KB|
| **InstanceUsageRate** |内存使用率|%|
| **InstanceConnCount** |当前连接数|个|
| **InstanceKeyNum** |总key个数|个|
| **InstanceBytesRead** |输入流量|Bps|
| **InstanceBytesWritten** |输出流量|Bps|
| **QPS** |总qps|次/s|
| **InstanceSetQPS** |setqps|次/s|
| **InstanceSetNum** |set操作数|次|
| **InstanceGetQPS** |getqps|次/s|
| **InstanceGetHitRate** |get命中率百分比|%|
| **InstanceGetNum** |get操作数|次|
| **InstanceDeleteNum** |delete操作数|次|
| **InstanceIncNum** |incr操作数|次|
| **InstanceDecrNum** |decr操作数|次|
| **InstanceTouchNum** |touch操作数|次|
| **InstanceCasNum** |cas操作数|次|
| **InstanceCpuUsage** |CPU负载|%|





#### ResourceType:umem
###### 云内存存储

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **InstanceUsage** |实例使用量|KB|
| **InstanceCount** |实例记录数|个|
| **InstanceGetQPS** |实例getQPS|次/s|
| **InstanceSetQPS** |实例setQPS|次/s|
| **InstanceDelQPS** |实例delQPS|次/s|
| **QPS** |实例总QPS|次/s|
| **InstanceGetHit** |实例GET_HIT数|次/s|
| **InstanceAddQPS** |实例ADD数|次/s|
| **InstanceReplaceQPS** |实例REPLACE数|次/s|
| **InstanceAppendQPS** |实例APPEND数|次/s|
| **InstancePrependQPS** |实例PREPEND数|次/s|
| **InstanceIncrQPS** |实例INRC数|次/s|
| **InstanceDecrQPS** |实例DECR数|次/s|
| **InstanceGetHitRate** |实例GET_HIT率|%|
| **PingErrorCount** |ping错误数|个|
| **Usage** |实例使用率|%|
| **BlockMaxUsage** |最大块内存使用率|%|
| **RedisAvgLoad** |平均负载|%|
| **RedisSiglenodeMaxload** |单点最高负载|%|
| **UMemInstanceConnCount** |实例连接数|次|
| **RequestTimeoutErrorCount** |请求超时次数|次|
| **OtherErrorCount** |其他错误|次|
| **RequestDelayErrorCount** |延迟次数|个|
| **UmemProxyMaxLoad** |代理最高负载|%|
| **UmemProxyAvgLoad** |代理平均负载|%|
| **UMemOutputBytes** |出带宽|Bps|
| **UMemInputBytes** |入带宽|Bps|
| **UMemFragmentationRatio** |碎片率|%|
| **UMemUsedMemoryDateset** |数据内存使用量|KB|
| **UMemBlockedClients** |阻塞连接|个|
| **UMemMissPerSec** |每秒miss率|次|
| **ProxyMaxLatency** |最大延迟|us|
| **ProxyAvgLatency** |平均延迟|us|
| **ProxyP99Latency** |p99延迟|us|





#### ResourceType:vpntunnel
###### VPN网关-隧道

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **VPNTunnelState** |vpngw隧道状态|bool|
| **SAOut** |隧道出流量|bps|
| **SAIn** |隧道入流量|bps|





#### ResourceType:tidb
###### 分布式NewSQL数据库

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **tidb_storage_size** |tidb实例存储量|Byte|
| **tidb_qps** |tidb实例qps|次/s|
| **tidb_tps** |tidb实例tps|次/s|
| **tidb_mem_usage** |tidb实例内存使用量|Byte|
| **tidb_query_duration_99** |sql 执行时间99值|ms|
| **tidb_query_duration_95** |sql 执行时间95值|ms|
| **tidb_query_duration_80** |sql 执行时间80值|ms|
| **tidb_tnx_duration_99** |事务执行时间99值|ms|
| **tidb_tnx_duration_95** |事务执行时间95值|ms|
| **tidb_tnx_duration_80** |事务执行时间80值|ms|
| **tidb_slow_query_duration_99** |慢查询执行时间99值|s|
| **tidb_slow_query_duration_95** |慢查询执行时间95值|s|
| **tidb_slow_query_duration_80** |慢查询执行时间80值|s|
| **tidb_parse_duration_99** |sql解析时间99值|ms|
| **tidb_parse_duration_95** |sql解析时间95值|ms|
| **tidb_parse_duration_80** |sql解析时间80值|ms|
| **tikv_apply_log_duration_99** |tikv  raftstore apply  log 时间99值|us|
| **tikv_apply_log_duration_95** |tikv  raftstore apply  log 时间95值|us|
| **tikv_apply_log_duration_avg** |tikv  raftstore apply  log 时间平均值|us|
| **tikv_append_log_duration_99** |tikv  raftstore append  log 时间99值|us|
| **tikv_append_log_duration_95** |tikv  raftstore append  log 时间95值|us|
| **tikv_append_log_duration_avg** |tikv  raftstore append  log 时间平均值|us|
| **tikv_cop_wait_duration_avg** |tikv coprocessor 平均等待时间|us|
| **tikv_cop_handle_time_avg_select** |tikv   coprocessor 平均处理时间select|ms|
| **tikv_cop_handle_time_avg_index** |tikv   coprocessor 平均处理时间index|ms|
| **tikv_block_cache_hit** |tikv块缓存命中率|%|
| **binlog_execute_time** |binglog写从库耗时|ms|
| **write_binlog_latency_99** |binglog写延时99值|ms|
| **write_binlog_latency_95** |binglog写延时95值|ms|
| **write_binlog_qps** |写binglog qps|次/s|
| **pump_storage_size** |tidb实例pump存储容量|Byte|
| **drainer_mem_usage** |tidb实例drainer内存使用量|Byte|
| **pump_mem_usage** |tidb实例pump内存使用量|Byte|
| **tiflash_mem_usage** |Tidb集群中TiFlash节点的内存使用量|Byte|
| **tiflash_storage_size** |Tidb集群中TiFlash节点的磁盘使用量|Byte|
| **tidb_connection_usage** |连接数使用率|%|





#### ResourceType:anycasteip
###### AnycastEIP

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **NetworkIn** |网络入口|bps|
| **NetworkOut** |网络出口|bps|
| **NetworkInUsage** |入口带宽使用率|%|
| **NetworkOutUsage** |出口带宽使用率|%|





#### ResourceType:natgw
###### NAT网关

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **BandOut** |gateway出向带宽|bps|
| **BandIn** |gateway入向带宽|bps|
| **FlowOut** |gateway出向流量|Byte|
| **FlowIn** |gateway入向流量|Byte|
| **PacketOut** |gateway出向包数|个|
| **PacketIn** |gateway入向包数|个|





#### ResourceType:urocketmq
###### RocketMQ消息队列

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **rocketmq_producer_tps** |每秒生产消息个数|个/s|
| **rocketmq_producer_message_size** |每秒生产数据|Bps|
| **rocketmq_consumer_tps** |每秒消费消息个数|个/s|
| **rocketmq_consumer_message_size** |每秒消费数据|Bps|
| **rocketmq_group_diff** |消息堆积个数|个|
| **rocketmq_group_get_latency_by_storetime** |消费延迟|ms|





#### ResourceType:ulb-vserver
###### 负载均衡监听器 VServer

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CurrentConnections** |ULBvserver当前连接数|个|
| **NetPacketIn** |ulb4的vserver每秒入包量|个/s|
| **NetPacketOut** |ulb4的vserver每秒出包量|个/s|
| **BandIn** |ulb4的vserver每秒入流量|bps|
| **BandOut** |ulb4的vserver每秒出流量|bps|
| **NewConnections** |ulb7前端VServer的新建连接数|个/s|
| **UlbVserverHrsp2xx** |ULBVServer每秒返回2XX的次数|个/s|
| **UlbVserverHrsp3xx** |ULBVServer每秒返回3XX的次数|个/s|
| **UlbVserverHrsp4xx** |ULBVServer每秒返回4XX的次数|个/s|
| **UlbVserverHrsp5xx** |ULBVServer每秒返回5XX的次数|个/s|
| **UlbVserverHrspOther** |ULBVServer每秒返回其它状态码的次数|个/s|
| **VServerQPS** |ulb7前端VServer的QPS|个/s|
| **VServerRT** |ulb7端口维度的请求平均时延|ms|
| **VServerUpstreamRT** |ulb7端口维度的后端响应平均时延|ms|





#### ResourceType:epc
###### 云极高性能计算EPC

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **RunnableProcessCount** |运行进程数目|个|
| **BlockProcessCount** |阻塞进程数目|个|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **ProcessCount** |进程总数|个|
| **TcpConnectCount** |TCP连接数|个|
| **LoadAvg1m** |loadavg1分钟||
| **LoadAvg5m** |loadavg5分钟||
| **LoadAvg15m** |loadavg15分钟||





#### ResourceType:connect
###### 混合云专线

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **BandIn** |流入带宽|bps|
| **BandOut** |流出带宽|bps|
| **PnRxRatePercent** |网络流入带宽使用率|%|
| **PnTxRatePercent** |网络流出带宽使用率|%|





#### ResourceType:kafka_group
###### Kafka消费组

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **KafkaConsumerLag** |消费者堆积消息|个|





#### ResourceType:upgsql
###### 云数据库 PgSQL

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **DiskUsage** |磁盘使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **MemSize** |内存大小|MB|
| **ConnectionCount** |连接数|个|
| **QPS** |QPS|次/s|
| **DeleteQPS** |删除QPS|次/s|
| **InsertQPS** |插入QPS|次/s|
| **SelectQPS** |查询QPS|次/s|
| **UpdateQPS** |更新QPS|次/s|
| **SlaveDelay** |从库同步延迟|s|
| **MemUsage** |内存使用率|%|
| **ExpensiveQuery** |慢查询|个|
| **SynchronizationError** |主从同步|个|
| **BackupFailed** |备份失败|次|
| **PingErrorCount** |db连通情况|个|
| **ReplaceQPS** |ReplaceQPS|次/s|
| **IOOps** |IO平均读写次数|次/s|
| **IO** |IO平均读写字节数|Bps|
| **AbReboot** |异常重启|次|
| **CoreFailure** |核心管理功能失效|次|
| **CPUCoreUsed** |CPU使用量(核数)|个|
| **DumpFailure** |DB备份导出失败||
| **IDHASlaveError** |高可用双主同步异常||
| **SandboxMemory** |DB系统总内存|MB|
| **SandboxCache** |DB系统总缓存|MB|
| **ServiceAvailability** |DB可用性错误||
| **TPS** |每秒事务数|次/s|
| **HAStandyDBDiskUsage** |高可用备主磁盘使用率|%|
| **HAHealthState** |高可用状态异常||
| **HASyncDelay** |高可用主备数据同步延时|s|
| **ActiveMemoryRatio** |活跃内存占比|%|
| **IOAwait** |磁盘的IO响应时间|ms|
| **IOUtilizationRatio** |IO利用率|%|
| **IOAverageQueueSize** |IO等待长度||
| **HaStandbyCPUUtilization** |高可用备库CPU使用率|%|
| **HaStandbyIOAverageQueueSize** |高可用备库IO等待长度|个/s|
| **HaStandbyMemUsage** |高可用备库内存使用率|%|
| **HaStandbyIOAwait** |高可用备库磁盘IO响应时间|ms|
| **HaStandbyIOUtilizationRatio** |高可用备库IO利用率|%|





#### ResourceType:utrafficpack
###### 共享流量包

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **TrafficPackageUsedSize** |共享流量包使用量|GB|
| **TrafficPackageAvailableSize** |共享流量包剩余量|GB|
| **TrafficPackageUsedPercent** |共享流量包使用量百分比|%|
| **TrafficPackageAvailablePercent** |共享流量包余量百分比|%|





#### ResourceType:upmdisk
###### 物理云磁盘

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **DiskUsage** |磁盘使用率|%|





#### ResourceType:umongodbmember
###### 云数据库 MongoDB UDB （NVMe）

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **DiskUsage** |磁盘使用率|%|
| **CPUUtilization** |CPU使用率|%|
| **MemSize** |内存大小|MB|
| **ConnectionCount** |连接数|个|
| **QPS** |QPS|次/s|
| **DeleteQPS** |删除QPS|次/s|
| **InsertQPS** |插入QPS|次/s|
| **SelectQPS** |查询QPS|次/s|
| **UpdateQPS** |更新QPS|次/s|
| **SlaveDelay** |从库同步延迟|s|
| **MemUsage** |内存使用率|%|
| **SynchronizationError** |主从同步|个|
| **BackupFailed** |备份失败|次|
| **PingErrorCount** |db连通情况|个|
| **ReplaceQPS** |ReplaceQPS|次/s|
| **IOOps** |IO平均读写次数|次/s|
| **IO** |IO平均读写字节数|Bps|
| **AbReboot** |异常重启|次|
| **CoreFailure** |核心管理功能失效|次|
| **CPUCoreUsed** |CPU使用量(核数)|个|
| **DumpFailure** |DB备份导出失败||
| **SandboxMemory** |DB系统总内存|MB|
| **SandboxCache** |DB系统总缓存|MB|
| **ServiceAvailability** |DB可用性错误||
| **ActiveMemoryRatio** |活跃内存占比|%|
| **MongoDBActiveClientReaders** |MongoDB正在读的客户端数|个|
| **MongoDBActiveClientWriters** |MongoDB正在写的客户端数|个|
| **MongoDBInsertOPCountsTotal** |MongoDB累计插入操作数|个|
| **MongoDBQueryOPCountsTotal** |MongoDB累计查询操作数|个|
| **MongoDBUpdateOPCountsTotal** |MongoDB累计更新操作数|个|
| **MongoDBDeleteOPCountsTotal** |MongoDB累计删除操作数|个|
| **MongoDBGetMoreOPCountsTotal** |MongoDB累计getMore操作数|个|
| **MongoDBCommandOPCountsTotal** |MongoDB累计执行管控命令操作数|个|
| **MongoDBCurrentQueueTotal** |MongoDB读写等待队列总长度|个|
| **MongoDBActiveConns** |MongoDB活跃连接数|个|
| **MongoDBWTCacheReadIntoSizeTotal** |MongoDB WT缓存读入累计数据量|Byte|
| **MongoDBWTCacheWrittenFromSizeTotal** |MongoDB WT缓存落盘累计数据量|Byte|
| **MongoDBWTMaxSize** |MongoDB WT缓存总大小|Byte|
| **MongoDBWTCacheUsage** |MongoDB WT缓存使用率|%|
| **MongoDBWTCacheDirtyUsage** |MongoDB WT缓存脏页占用率|%|
| **MongoDBWTReadFromDiskSizeTotal** |MongoDB WT磁盘读取累计数据量|Byte|
| **MongoDBWTWrittenIntoDiskSizeTotal** |MongoDB WT磁盘写入累计数据量|Byte|
| **MongoDBCurrentQueueReaders** |MongoDB当前等待读队列长度|个|
| **MongoDBCurrentQueueWriters** |MongoDB当前等待写队列长度|个|
| **IOUtilizationRatio** |IO利用率|%|





#### ResourceType:udbproxymember
###### 云数据库读写分离中间件

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **UDBProxyConnPoolLen** |缓存的连接数|个|
| **UDBProxyGetSuccessUsage** |获取连接池缓存成功率|%|
| **UDBProxyPutSuccessUsage** |回收连接成功率|%|
| **UDBProxyCPUUsage** |cpu使用率|%|
| **UDBProxyMemUsage** |内存使用率|%|
| **UDBProxyQps** |qps数|次/s|
| **UDBProxyConnectionCount** |连接数|次/s|
| **UDBProxySelectSqlCount** |select数|次/s|
| **UDBProxyInsertSqlCount** |insert数|次/s|
| **UDBProxyUpdateSqlCount** |update数|次/s|
| **UDBProxyDeleteSqlCount** |delete数|次/s|
| **UDBProxyPrepareSqlCount** |prepare数|次/s|





#### ResourceType:ugnbw
###### 云联网带宽包

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **UgnBWOutbps** |出向带宽|bps|
| **UgnBWOutPeakbps** |出向峰值带宽|bps|
| **UgnBWOutUsage** |出向带宽使用率|%|
| **UgnBWOutPeakUsage** |出向峰值带宽使用率|%|
| **UgnBWOutpps** |出向包量|个/s|





#### ResourceType:uhostdiskpart
###### 磁盘分区

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **DiskpartUsage** |磁盘分区空间使用率|%|
| **DiskpartInodeUsage** |磁盘分区inode使用率|%|





#### ResourceType:als
###### ALB监听器

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CurrentConnections** |ULBvserver当前连接数|个|
| **NewConnections** |ulb7前端VServer的新建连接数|个/s|
| **ListenerHrsp2xx** |监听器每秒返回2XX的次数|个/s|
| **ListenerHrsp3xx** |监听器每秒返回3XX的次数|个/s|
| **ListenerHrsp4xx** |监听器每秒返回4XX的次数|个/s|
| **ListenerHrsp5xx** |监听器每秒返回5XX的次数|个/s|
| **ListenerHrspOther** |监听器每秒返回其它状态码的次数|个/s|
| **ListenerQPS** |监听器每秒请求数|个/s|
| **ListenerRSDownPercent** |监听器的节点失效百分比|%|
| **ListenerRT** |监听器的请求平均时延|ms|
| **ListenerUpstreamRT** |监听器的后端响应平均时延|ms|





#### ResourceType:lbip
###### LB内网VIP

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **InternalInBPS** |内网ulb7每秒入比特数|bps|
| **InternalInPPS** |内网ulb7每秒入包量|个/s|
| **InternalOutBPS** |内网ulb7每秒出比特数|bps|
| **InternalOutPPS** |内网ulb7每秒出包量|个/s|





#### ResourceType:uhost_gpu
###### 主机GPU卡

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **GPUUtil** |GPU卡使用率|%|
| **GPUUncorrECC** |GPU卡ecc纠错|次|
| **GPUDriverDetectable** |GPU卡驱动可识别性||
| **GPUMemoryUsed** |GPU卡显存使用量|MB|
| **GPUMemoryUsage** |GPU卡显存使用率|%|





#### ResourceType:uwsc-tunnel
###### UWAN智联-VPN隧道

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **UWANTunnelOutBW** |UWAN隧道出向流量|bps|
| **UWANTunnelInBW** |UWAN隧道入向流量|bps|





#### ResourceType:uwsc-bandwidth
###### UWAN智联-接入带宽包

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **UWANOutBW** |UWAN接入带宽包-出向流量|bps|
| **UWANInBW** |UWAN接入带宽包-入向流量|bps|





#### ResourceType:ufile
###### 对象存储

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **HaikangNetOutcoming** |海康网络出向流量|Byte|
| **BucketDownloadFlow** |下载流量|Byte|
| **BucketUploadFlow** |上传流量|Byte|
| **BucketTotalStorage** |标准存储量|Byte|
| **BucketUploadInnerFlow** |内网上传流量(不计费)|Byte|
| **BucketDownloadInnerFlow** |内网下载流量(不计费)|Byte|
| **BucketUploadCount** |bucket总上传数|次|
| **BucketDownloadCount** |bucket总下载数|次|
| **BucketDeleteCount** |bucket总删除数|次|
| **Bucket5xxError** |5xx错误|次|
| **BucketCdnFlow** |UCDN回源流量|Byte|
| **BucketIaRetrieval** |低频取回量|Byte|
| **BucketArchiveRetrieval** |归档解冻量|Byte|
| **BucketIaMinStorage** |低频最短存储量|Byte|
| **BucketArchiveMinStorage** |冷存最短存储量|Byte|
| **BucketIaStorages** |低频存储量|Byte|
| **BucketArchiveStorages** |归档存储量|Byte|
| **Bucket2xxStatus** |2xx请求发生次数|次|
| **Bucket4xxStatus** |4xx请求发生次数|次|
| **BucketDownLoadSuccess** |下载成功数|次|
| **BucketUploadSuccess** |上传成功数|次|
| **BucketDownLoadError** |下载超时错误数|次|
| **BucketUploadError** |上传超时错误数|次|
| **BucketRequestTotal** |总请求数|次|
| **HaikangNetIncoming** |海康网络入向流量|Byte|
| **HaikangIcmpLoss** |海康icmp丢包率|%|
| **HaikangNetErrors** |海康网卡错误数|个|
| **image_handle_flow** |图片处理流量|Byte|
| **image_compress_count** |图片高级压缩次数|次|
| **BucketArchiveExpeditedRetrieval** |归档紧急解冻量|Byte|





#### ResourceType:uclickhouse
###### 云数据仓库Uclickhouse

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **uclickhouse_query** |每秒Query个数|个/s|
| **uclickhouse_insert_query** |每秒Insert个数|个/s|
| **uclickhouse_select_query** |每秒Select个数|个/s|
| **uclickhouse_failed_query** |失败Query个数|个/s|
| **uclickhouse_failed_insert_query** |每秒失败Insert Query个数|个/s|
| **uclickhouse_failed_select_query** |每秒失败Select Query个数|个/s|
| **uclickhouse_delayed_inserts** |每秒延迟Insert个数|个/s|
| **uclickhouse_merge** |运行Merge个数|个|
| **uclickhouse_part_mutation** |运行Mutation个数|个|
| **uclickhouse_inserted_rows** |每秒写入行数|行/s|
| **uclickhouse_parts_active** |Data Part个数|个|
| **uclickhouse_parts_outdated** |Inactive Data Part 个数|个|
| **uclickhouse_inserted_bytes** |每秒写入大小|Bps|
| **uclickhouse_qps** |QPS||
| **uclickhouse_tps** |TPS||
| **uclickhouse_query_thread** |查询线程数|个|
| **uclickhouse_tcp_connection** |TCP连接数|个|
| **uclickhouse_http_connection** |HTTP连接数|个|
| **uclickhouse_mysql_connection** |MySQL连接数|个|
| **uclickhouse_running_query** |运行Query个数|个|





#### ResourceType:uclickhousenode
###### 云数据仓库UClickhouse节点

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **uclickhousenode_disk_write_ops** |数据盘写吞吐|Bps|
| **uclickhousenode_io_read** |数据盘读次数|次/s|
| **uclickhousenode_io_write** |数据盘写次数|次/s|
| **uclickhousenode_network_in** |网卡入带宽|Bps|
| **uclickhousenode_network_out** |网卡出带宽|Bps|
| **uclickhousenode_data_disk_usage** |数据盘使用率|%|
| **uclickhousenode_cpu_usage** |CPU使用率|%|
| **uclickhousenode_memory_usage** |内存使用率|%|
| **uclickhousenode_inserted_rows** |每秒写入行数|行/s|
| **uclickhousenode_query** |每秒Query个数|个/s|
| **uclickhousenode_insert_query** |每秒Insert个数|个/s|
| **uclickhousenode_select_query** |每秒Select个数|个/s|
| **uclickhousenode_failed_query** |失败Query个数|个/s|
| **uclickhousenode_failed_insert_query** |每秒失败Insert Query个数|个/s|
| **uclickhousenode_failed_select_query** |每秒失败Select Query个数|个/s|
| **uclickhousenode_delayed_inserts** |每秒延迟Insert个数|个/s|
| **uclickhousenode_merge** |运行Merge个数|个|
| **uclickhousenode_part_mutation** |运行Mutation个数|个|
| **uclickhousenode_disk_read_ops** |数据盘读吞吐|Bps|
| **uclickhousenode_parts_active** |Data Part个数|个|
| **uclickhousenode_parts_outdated** |Inactive Data Part个数|个|
| **uclickhousenode_inserted_bytes** |每秒写入大小|Bps|
| **uclickhousenode_qps** |QPS||
| **uclickhousenode_tps** |TPS||
| **uclickhousenode_query_thread** |查询线程数|个|
| **uclickhousenode_tcp_connection** |TCP连接数|个|
| **uclickhousenode_http_connection** |HTTP连接数|个|
| **uclickhousenode_mysql_connection** |MySQL连接数|个|
| **uclickhousenode_running_query** |运行Query个数|个|





#### ResourceType:ulogstash-node
###### ULogstash-Node

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|





#### ResourceType:ulhost
###### 轻量应用云主机

| 参数                    |描述信息|单位|
|:----------------------|:---|:---|
| **CPUUtilization** |CPU使用率|%|
| **IORead** |磁盘读流量|Bps|
| **IOWrite** |磁盘写流量|Bps|
| **DiskReadOps** |磁盘读次数|次/s|
| **DiskWriteOps** |磁盘写次数|次/s|
| **NICIn** |网卡入带宽|bps|
| **NICOut** |网卡出带宽|bps|
| **NetPacketIn** |网卡入包量|个/s|
| **NetPacketOut** |网卡出包量|个/s|
| **MemUsage** |内存使用率|%|
| **DataSpaceUsage** |数据盘磁盘空间使用率|%|
| **RootSpaceUsage** |系统盘磁盘空间使用率|%|
| **RunnableProcessCount** |运行进程数目|个|
| **BlockProcessCount** |阻塞进程数目|个|
| **ReadonlyDiskCount** |云主机只读磁盘个数|个|
| **ProcessCount** |进程总数|个|
| **TcpConnectCount** |TCP连接数|个|
| **LoadAvg1m** |loadavg1分钟||
| **LoadAvg5m** |loadavg5分钟||
| **LoadAvg15m** |loadavg15分钟||
| **CPUIOWait** |CPU IOWait率|%|
| **ULHostTrafficPackageUsedSize** |轻量流量包使用量|GB|
| **ULHostTrafficPackageUsedPercent** |轻量流量包使用量百分比|%|
| **ULHostTrafficPackageAvailablePercent** |轻量流量包余量百分比|%|
| **ULHostTrafficPackageAvailableSize** |轻量流量包剩余量|GB|


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
