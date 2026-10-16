# 获取账单明细 - ListUBillDetail

## 简介

获取某个账期内的所有消费。

?> 获取当月账单明细一般存在一天延迟。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUBillDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BillingCycle** | string | 账期，YYYY-MM，比如2021-08，只支持2018-05之后的查询 |**Yes**|
| **ProjectName** | string | 项目名称 (筛选项, 默认全部)	 |No|
| **ResourceIds.N** | string | 资源ID(筛选项, 默认全部)	<br />支持多筛选，多筛选请在请求参数中添加多个字段<br />例<br />ResourceIds.0: uhost-bzgf1gh5，<br />ResourceIds.1: uhost-gu1xpspa，<br /> |No|
| **OrderType** | string | 订单类型 (筛选项, 默认全部) 。枚举值：<br /><br /> > OT_BUY:新购 <br /><br /> > OT_RENEW:续费 <br /><br /> > OT_UPGRADE:升级 <br /><br /> > OT_DOWNGRADE:降级 <br /><br /> > OT_SUSPEND:结算 <br /><br /> > OT_ADDITIONAL:补单 <br /><br /> > OT_REFUND:删除 <br /><br /> > OT_POSTPAID_RENEW:过期 <br /><br /> > OT_POSTPAID_PAYMENT:后付费 <br /><br /> > OT_RECOVER:删除恢复  |No|
| **ChargeType** | string | 计费方式 (筛选项, 默认全部)。枚举值：<br /><br /> > Year:按年<br /><br /> > Month:按月 <br /><br /> > Day:按天 <br /><br /> > Dynamic:按时  <br /><br /> > Used:按量 <br /><br /> > Donate:赠送 <br /><br /> > Trial:试用  <br /><br /> > Post:后付费  <br /><br /> > Spot:抢占式 |No|
| **ShowZero** | int | 是否显示0元订单 (0 不显示, 1 显示, 默认0) |No|
| **PaidState** | int | 支付状态 (筛选项, 1:仅显示未支付订单; 2:仅显示已支付订单; 0:两者都显示)	    当前月份 传递1或者0，会返回历史所有未支付账单；历史月份不支持查询未支付，请勿传递1 |No|
| **UserEmail** | string | 用户邮箱，可以根据用户邮箱来进行筛选 |No|
| **Limit** | int | 每页数量，默认值25，最大值：100。 |No|
| **Offset** | int | 数据偏移量 (默认0)	 |No|
| **ResourceTypes.N** | string | 产品类型 (筛选项, 默认全部),<br />支持多筛选，多筛选请在请求参数中添加多个字段。枚举值：<br /><br /> > uhost:云主机 <br /><br /> > udisk:普通云硬盘 <br /><br /> > udisk_ssd:SSD云硬盘 <br /><br /> > rssd:RSSD云硬盘 <br /><br /> > snapshot:云快照 <br /><br /> > uimage:云主机镜像 <br /><br /> > isolation_group:硬件隔离组 <br /><br /> > udisk_system_disk:云硬盘系统盘 <br /><br /> > phost:裸金属云主机 <br /><br /> > udset:资源池 <br /><br /> > udhost:专区宿主 <br /><br /> > rack:托管云机位 <br /><br /> > hybrid_rack:托管云机柜 <br /><br /> > hybrid_machine:托管云物理机 <br /><br /> > userver:金翼物理机 <br /><br /> > hybrid_host:托管云物理云主机 <br /><br /> > hybrid_vip_service:启明VIP服务 <br /><br /> > hybrid_public_net:外网-IP段 <br /><br /> > hybrid_public_bw:外网-带宽 <br /><br /> > rack_bw:网络 <br /><br /> > ulink:内网-云互通 <br /><br /> > hybrid_others:耗材 <br /><br /> > uconnect:专线 <br /><br /> > hybrid_switch:交换机 <br /><br /> > hybrid_port:交换机端口 <br /><br /> > shared_bandwidth:共享带宽 <br /><br /> > eip:弹性IP <br /><br /> > traffic:流量 <br /><br /> > bandwidth:带宽包 <br /><br /> > vpn:VPN网关 <br /><br /> > firewall:防火墙 <br /><br /> > vip:内网IP <br /><br /> > UAnycastClean:Anycast全球清洗防护包 <br /><br /> > AnycastEIP:AnycastEIP <br /><br /> > ulb:负载均衡 <br /><br /> > vlb:专享型ULB <br /><br /> > ssl:证书管理 <br /><br /> > subnet:子网 <br /><br /> > natgw:NAT网关 <br /><br /> > vpc:虚拟私有网络 <br /><br /> > acl:访问控制列表 <br /><br /> > udpn:高速通道 <br /><br /> > vpngw:VPN网关 <br /><br /> > remotevpngw:客户网关 <br /><br /> > vpn_tunnel:隧道 <br /><br /> > udee:域名要素引擎 <br /><br /> > ugaa:全球动态加速 <br /><br /> > upath:线路管理 <br /><br /> > Roma:罗马 <br /><br /> > ufs:文件存储 <br /><br /> > ufile:对象存储 <br /><br /> > udataark:数据方舟 <br /><br /> > uarchive:归档存储 <br /><br /> > ucdn:云分发 <br /><br /> > uodn:开放式分发节点 <br /><br /> > uodn2:边缘分发节点 <br /><br /> > umem:云内存存储 <br /><br /> > umemcache:单机版memcache <br /><br /> > uredis:主备版redis <br /><br /> > udb:云数据库 <br /><br /> > mongodb:MongoDB <br /><br /> > sqlserver:SQLServer <br /><br /> > postgresql:PostgreSQL <br /><br /> > utsdb:时序数据库 <br /><br /> > uddb:分布式数据库 <br /><br /> > tidb:分布式NewSQL数据库 <br /><br /> > Hadoop:托管Hadoop集群 <br /><br /> > HadoopHost:托管Hadoop集群节点 <br /><br /> > udw:云数据仓库 <br /><br /> > ues:弹性搜索 <br /><br /> > uscheduler:调度系统 <br /><br /> > ukafka:Kafka消息队列 <br /><br /> > usql_end:数据湖分析 <br /><br /> > UFlink:Flink实时计算 <br /><br /> > ukafka_host:Kafka消息队列节点 <br /><br /> > UKafkaSinker:Kafka连接器 <br /><br /> > message_queue:消息队列 <br /><br /> > UAPIGateway:API网关 <br /><br /> > ucs:通用计算 <br /><br /> > docker_uhost:节点 <br /><br /> > uiot:UIoT-Core <br /><br /> > uai_service:AI在线服务 <br /><br /> > uai_training:AI训练服务 <br /><br /> > UAI-Censor:AI内容审核 <br /><br /> > uvideo:云点播 <br /><br /> > ulive:云直播 <br /><br /> > umedia:媒体工厂 <br /><br /> > VideoSDK:视频工具 <br /><br /> > UKMS:密钥管理服务 <br /><br /> > SDefense:高防 <br /><br /> > ADS-HD:华东高防 <br /><br /> > ADS-abroad:海外高防 <br /><br /> > uclean:清洗 <br /><br /> > waf:WEB应用防火墙 <br /><br /> > uws:WEB漏洞扫描 <br /><br /> > uhids:主机入侵检测 <br /><br /> > uencrypt:加密服务 <br /><br /> > fortress_host:堡垒机 <br /><br /> > db_audit:数据库审计 <br /><br /> > usa:云安全中心 <br /><br /> > udbcp:等保咨询 <br /><br /> > usms:短信包 <br /><br /> > udnr:域名注册服务 <br /><br /> > hegui:备案 <br /><br /> > ussl:SSL证书唯一标识 <br /><br /> > umarket:应用市场 <br /><br /> > urtc:实时音视频 <br /><br /> > umr:MapReduce <br /><br /> > utss:UCloud技术支持服务 <br /><br /> > store_box:店铺盒子 <br /><br /> > ukv:容量型KV存储 <br /><br /> > ucloudperation:云合作 <br /><br /> > umon_network:网络质量监控 <br /><br /> > uaccess_box:UBox <br /><br /> > UOPS:运维服务 <br /><br /> > TeuProduct:非标-企业 <br /><br /> > TeuHumanResource:服务-企业 <br /><br /> > UBI:数据可视化分析 <br /><br /> > First_tier_Bandwidth:ODN一线城市带宽 <br /><br /> > Second_tier_Bandwidth:ODN二线城市带宽 <br /><br /> > ODN-EDU-BW:ODN教育网带宽 <br /><br /> > uodn_docker_resource:ODN容器 <br /><br /> > UAI-Solution:AI解决方案 <br /><br /> > USNAPSHOT:磁盘快照服务 <br /><br /> > ServiceFee:一次性收费 <br /><br /> > UCloudAntiDDoS-NorthChinaBGP:高防-华北BGP <br /><br /> > Cube:容器实例 <br /><br /> > UHybrid-EBN:混合云-企业网 <br /><br /> > UHybrid-VBS:混合云-虚拟边界交换机 <br /><br /> > UHybrid-EBNBandwidth:混合云-企业网带宽 <br /><br /> > UCGS:云游戏 <br /><br /> > USDP:智能大数据平台 <br /><br /> > UIoT-Stack:物联网平台系统套件 <br /><br /> > uiotedgebox:物联网边缘盒子 <br /><br /> > UClickhouse:云数据库仓库UClickHouse <br /><br /> > UDNS:云解析 <br /><br /> > UFS-SMB:SMB文件系统 <br /><br /> > EPC:云极高性能计算节点 <br /><br /> > EPCCluster:高性能计算集群 <br /><br /> > Instance:海外站云主机 <br /><br /> > UGA3:全球动态加速 <br /><br /> > uhybrid_xzone:混合云-金翼XZone <br /><br /> > udts:数据传输服务 <br /><br /> > uk8s_service:容器云 <br /><br /> > UIW:无间盾反欺诈系统 <br /><br /> > ISMS:视频短信 <br /><br /> > PLiveUPRO:Polyv云直播U享版 <br /><br /> > UNVS:号码认证 <br /><br /> > UVMS:语音消息服务 <br /><br /> > UGame:云游戏 <br /><br /> > UHive:UHive <br /><br /> > UDoris:UDoris <br /><br /> > USLK:短链工具 <br /><br /> > UPCA:UPCA <br /><br /> > URCM:富信消息 <br /><br /> > HTTPDNS:HTTP DNS <br /><br /> > UAdsSp:DDOS防御服务包 <br /><br /> > UPhone-eip:云手机（eip） <br /><br /> > UPhone-share-bandwidth:云手机（共享带宽） <br /><br /> > UCloud Phone Server:云手机服务器 <br /><br /> > UMongoDBMember:云数据库 MongoDB UDB 集群内节点成员 <br /><br /> > UPhone-NetworkResource:云手机（网络资源） <br /><br /> > UOL:海外直播加速 <br /><br /> > UDBProxy:云数据库读写分离中间件 <br /><br /> > UDBProxyMember:云数据库读写分离中间件集群内成员 <br /><br /> > UPgSQL:UDB For PgSQL <br /><br /> > UMongoDB:UMongoDB <br /><br /> > UPresto:UPresto <br /><br /> > UDBC:UDBC <br /><br /> > CAAS:CAAS <br /><br /> > UPhone:云手机 <br /><br /> > NVAS:混合云-网络增值服务 <br /><br /> > UNPP:号码隐私保护 <br /><br /> > UNPP:企业名片 <br /><br /> > UMongoDBVirtualMember:云数据库 MongoDB UDB集群内虚拟节点 <br /><br /> > CF-antiddos:CF高防服务 <br /><br /> > UAM:优信 <br /><br /> > UAIModelFactory:人工智能模型工厂 <br /><br /> > UGNBW:云联网带宽包 <br /><br /> > UDAS:数据库自治服务 <br /><br /> > URM:资源迁移 <br /><br /> > UDTS-DI:数据传输服务-数据集成 <br /><br /> > ALB:应用型负载均衡 <br /><br /> > UTrafficPack:共享流量包 <br /><br /> > ULHost:轻量应用云主机 <br /><br /> > UWSCBandwith:UWAN智联-接入带宽包 <br /><br /> > MySQLBackup:MySQL 备份服务 <br /><br /> > SkyMirror:天镜 <br /><br /> > UCustomImage:自定义镜像 <br /><br /> > UDTS-DIS:数据传输服务-数据集成子任务 <br /><br /> > utm:流量镜像 <br /><br /> > NLB:网络型负载均衡 <br /><br /> > ALS:ALB监听器 <br /><br /> > NLS:NLB监听器 <br /><br /> > ARS:ALB服务节点 <br /><br /> > NRS:NLB服务节点 <br /><br /> > UAIM:卡片消息 <br /><br /> > UWSC:UWAN智联 <br /><br /> > LBIP:负载均衡内网IP <br /><br /> > ULogstash:Logstash服务 <br /><br /> > UWCE:UWAN智联-CE客户网关 <br /><br /> > UWSC-Tunnel:UWAN智联-VPN隧道 <br /><br /> > UNDT:网络拨测 <br /><br /> > UHBW:托管带宽包 <br /><br /> > UHNet:托管网络 <br /><br /> > UH-VRrouter:托管虚拟路由器 <br /><br /> > XC:楼内线 <br /><br /> > UModelVerse:模型服务平台 <br /><br /> > ULogstash-Node:Logstash Node服务 <br /><br /> > CloudWatch:云监控 <br /><br /> > UGN:云联网 <br /><br /> > epsrv:终端节点服务 <br /><br /> > ep:终端节点 <br /><br /> > uwcpe:CPE智能网关 <br /><br /> > uwcpetunnel:CPE隧道 <br /><br /> > USCS:安全定制服务 <br /><br /> > UAAA:应用仓库加速 <br /><br /> > ULogService:日志服务 <br /><br /> > UXZONE-GPU:金翼GPU <br /><br /> > UReach:优睿达 <br /><br /> > UPLVR:专线虚拟路由器 <br /><br /> > maxir:云数据仓库MAXIR <br /><br /> > maxirvector:云数据仓库MAXIR向量版 <br /><br /> > UPFS:文件存储UPFS <br /><br /> > UMarketplace:云市场 <br /><br /> > IPRP:IP资源池 <br /><br /> > ExclusiveHosts:包销宿主机 <br /><br /> > RedisReplicate:Redis 从库 <br /><br /> > SecurityCenter:云安全中心 <br /><br /> > PrivateLink:私有链接 <br /><br /> > UMongoDBBackup:MongoDB备份服务 <br /><br /> > TiDBCluster:分布式数据库 TiDB Cluster <br /><br /> > MAXIRDPS:MAXIR DPS <br /><br /> > Label:标签 <br /><br /> > NVAS:混合云网络增值服务 <br /><br /> > UIBUDS:互联网事业部开发服务 <br /><br /> > KafkaGroup:Kafka消费组 <br /><br /> > RLM:实时无损监控告警 <br /><br /> > USG:安全组 <br /><br /> > CF-antiddos:CF高防服务 <br /><br /> > UClickhouseNode:云数据仓库UClickhouse节点 <br /><br /> > HPCExpress:盘柜直达服务 <br /><br /> > UDI:数据智能 <br /><br /> > UMountPoint:文件系统挂载点 <br /><br /> > UPrometheus:托管Prometheus服务 <br /><br /> > AnycastCleanPromotion:全球清洗促销 <br /><br /> > USMC:服务器迁移中心 <br /><br /> > UK8SPod:UK8SPod 类型资源 <br /><br /> > UAS:弹性伸缩 <br /><br /> > Manul:统一存储 <br /><br /> > UDas:分部式应用服务 <br /><br /> > USecLog:安全日志审计 <br /><br /> > UKafkaSinkerNode:Kafka连接器节点 <br /><br /> > IPv6Address:IPv6地址 <br /><br /> > UFlink-Node:Flink实时计算节点 <br /><br /> > UContract:电子合同 <br /><br /> > NAT64:IPv6转换 <br /><br /> > OBJ_TYPE_UDDBAC:UDDB分析节点 <br /><br /> > OBJ_TYPE_SYS_UDISK_SSD:SSD云硬盘系统盘 <br /><br /> > utoken:令牌服务 <br /><br /> > UATP:API测试平台 <br /><br /> > udb_region:跨可用区高可用数据库 <br /><br /> > compshareImage:算力镜像 <br /><br /> > commImage:算力社区镜像 <br /><br /> > MAXIR AI:知识洞察 <br /><br /> > UCNest:算力云巢 <br /><br /> > IPV6 Gateway:IPV6公网网关 <br /><br /> > UCNest ExIP:算力云巢外网IP <br /><br /> > IPV6 Address:IPV6地址 <br /><br /> > UDBProxy RoGroup for MySQL:数据库代理只读组 <br /><br /> > SSD Essential:经济型SSD云盘 <br /><br /> > RSSD Essential:经济型RSSD云盘 <br /><br /> > RocketMQ Message Queue Node:消息队列节点 <br /><br /> > Runc Instance:Runc 实例 <br /><br /> > Runc Image:Runc 镜像 <br /><br /> > UCDC:专属云平台服务 <br /><br /> > Other:其他 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Items** | array[[*BillDetailItem*](#BillDetailItem)] | 账单明细数组 |**Yes**|
| **TotalCount** | int | 账单明细总长度 |**Yes**|

#### 数据模型


#### BillDetailItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目id |**Yes**|
| **Amount** | string | 订单总金额 |**Yes**|
| **AmountReal** | string | 现金账户支付 |**Yes**|
| **AmountFree** | string | 赠送金额抵扣 |**Yes**|
| **AmountCoupon** | string | 代金券抵扣 |**Yes**|
| **AzGroupCName** | string | 可用区 |**Yes**|
| **ChargeType** | string | 计费方式 (筛选项, 默认全部)。枚举值：<br /><br /> > Year:按年<br /><br /> > Month:按月 <br /><br /> > Day:按天 <br /><br /> > Dynamic:按时 <br /><br /> > Used:按量 <br /><br /> > Donate:赠送 <br /><br /> > Trial:试用 <br /><br /> > Post:后付费 <br /><br /> > Spot:抢占式 |**Yes**|
| **CreateTime** | int | 创建时间（时间戳） |**Yes**|
| **StartTime** | int | 开始时间（时间戳） |**Yes**|
| **EndTime** | int | 结束时间（时间戳） |**Yes**|
| **OrderNo** | string | 订单号 |**Yes**|
| **OrderType** | string | 订单类型 (筛选项, 默认全部) 。枚举值：<br /><br /> > OT_BUY:新购 <br /><br /> > OT_RENEW:续费 <br /><br /> > OT_UPGRADE:升级 <br /><br /> > OT_DOWNGRADE:降级 <br /><br /> > OT_SUSPEND:结算 <br /><br /> > OT_ADDITIONAL:补单 <br /><br /> > OT_REFUND:删除 <br /><br /> > OT_POSTPAID_RENEW:过期 <br /><br /> > OT_POSTPAID_PAYMENT:后付费 <br /><br /> > OT_RECOVER:删除恢复 |**Yes**|
| **ProjectName** | string | 项目名称 |**Yes**|
| **BusinessGroup** | string | 业务组 |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **ResourceType** | string | 产品类型 (筛选项, 默认全部),<br />支持多筛选，多筛选请在请求参数中添加多个字段。枚举值：<br /><br /> > uhost:云主机 <br /><br /> > udisk:普通云硬盘 <br /><br /> > udisk_ssd:SSD云硬盘 <br /><br /> > rssd:RSSD云硬盘 <br /><br /> > snapshot:云快照 <br /><br /> > uimage:云主机镜像 <br /><br /> > isolation_group:硬件隔离组 <br /><br /> > udisk_system_disk:云硬盘系统盘 <br /><br /> > phost:裸金属云主机 <br /><br /> > udset:资源池 <br /><br /> > udhost:专区宿主 <br /><br /> > rack:托管云机位 <br /><br /> > hybrid_rack:托管云机柜 <br /><br /> > hybrid_machine:托管云物理机 <br /><br /> > userver:金翼物理机 <br /><br /> > hybrid_host:托管云物理云主机 <br /><br /> > hybrid_vip_service:启明VIP服务 <br /><br /> > hybrid_public_net:外网-IP段 <br /><br /> > hybrid_public_bw:外网-带宽 <br /><br /> > rack_bw:网络 <br /><br /> > ulink:内网-云互通 <br /><br /> > hybrid_others:耗材 <br /><br /> > uconnect:专线 <br /><br /> > hybrid_switch:交换机 <br /><br /> > hybrid_port:交换机端口 <br /><br /> > shared_bandwidth:共享带宽 <br /><br /> > eip:弹性IP <br /><br /> > traffic:流量 <br /><br /> > bandwidth:带宽包 <br /><br /> > vpn:VPN网关 <br /><br /> > firewall:防火墙 <br /><br /> > vip:内网IP <br /><br /> > UAnycastClean:Anycast全球清洗防护包 <br /><br /> > AnycastEIP:AnycastEIP <br /><br /> > ulb:负载均衡 <br /><br /> > vlb:专享型ULB <br /><br /> > ssl:证书管理 <br /><br /> > subnet:子网 <br /><br /> > natgw:NAT网关 <br /><br /> > vpc:虚拟私有网络 <br /><br /> > acl:访问控制列表 <br /><br /> > udpn:高速通道 <br /><br /> > vpngw:VPN网关 <br /><br /> > remotevpngw:客户网关 <br /><br /> > vpn_tunnel:隧道 <br /><br /> > udee:域名要素引擎 <br /><br /> > ugaa:全球动态加速 <br /><br /> > upath:线路管理 <br /><br /> > Roma:罗马 <br /><br /> > ufs:文件存储 <br /><br /> > ufile:对象存储 <br /><br /> > udataark:数据方舟 <br /><br /> > uarchive:归档存储 <br /><br /> > ucdn:云分发 <br /><br /> > uodn:开放式分发节点 <br /><br /> > uodn2:边缘分发节点 <br /><br /> > umem:云内存存储 <br /><br /> > umemcache:单机版memcache <br /><br /> > uredis:主备版redis <br /><br /> > udb:云数据库 <br /><br /> > mongodb:MongoDB <br /><br /> > sqlserver:SQLServer <br /><br /> > postgresql:PostgreSQL <br /><br /> > utsdb:时序数据库 <br /><br /> > uddb:分布式数据库 <br /><br /> > tidb:分布式NewSQL数据库 <br /><br /> > Hadoop:托管Hadoop集群 <br /><br /> > HadoopHost:托管Hadoop集群节点 <br /><br /> > udw:云数据仓库 <br /><br /> > ues:弹性搜索 <br /><br /> > uscheduler:调度系统 <br /><br /> > ukafka:Kafka消息队列 <br /><br /> > usql_end:数据湖分析 <br /><br /> > UFlink:Flink实时计算 <br /><br /> > ukafka_host:Kafka消息队列节点 <br /><br /> > UKafkaSinker:Kafka连接器 <br /><br /> > message_queue:消息队列 <br /><br /> > UAPIGateway:API网关 <br /><br /> > ucs:通用计算 <br /><br /> > docker_uhost:节点 <br /><br /> > uiot:UIoT-Core <br /><br /> > uai_service:AI在线服务 <br /><br /> > uai_training:AI训练服务 <br /><br /> > UAI-Censor:AI内容审核 <br /><br /> > uvideo:云点播 <br /><br /> > ulive:云直播 <br /><br /> > umedia:媒体工厂 <br /><br /> > VideoSDK:视频工具 <br /><br /> > UKMS:密钥管理服务 <br /><br /> > SDefense:高防 <br /><br /> > ADS-HD:华东高防 <br /><br /> > ADS-abroad:海外高防 <br /><br /> > uclean:清洗 <br /><br /> > waf:WEB应用防火墙 <br /><br /> > uws:WEB漏洞扫描 <br /><br /> > uhids:主机入侵检测 <br /><br /> > uencrypt:加密服务 <br /><br /> > fortress_host:堡垒机 <br /><br /> > db_audit:数据库审计 <br /><br /> > usa:云安全中心 <br /><br /> > udbcp:等保咨询 <br /><br /> > usms:短信包 <br /><br /> > udnr:域名注册服务 <br /><br /> > hegui:备案 <br /><br /> > ussl:SSL证书唯一标识 <br /><br /> > umarket:应用市场 <br /><br /> > urtc:实时音视频 <br /><br /> > umr:MapReduce <br /><br /> > utss:UCloud技术支持服务 <br /><br /> > store_box:店铺盒子 <br /><br /> > ukv:容量型KV存储 <br /><br /> > ucloudperation:云合作 <br /><br /> > umon_network:网络质量监控 <br /><br /> > uaccess_box:UBox <br /><br /> > UOPS:运维服务 <br /><br /> > TeuProduct:非标-企业 <br /><br /> > TeuHumanResource:服务-企业 <br /><br /> > UBI:数据可视化分析 <br /><br /> > First_tier_Bandwidth:ODN一线城市带宽 <br /><br /> > Second_tier_Bandwidth:ODN二线城市带宽 <br /><br /> > ODN-EDU-BW:ODN教育网带宽 <br /><br /> > uodn_docker_resource:ODN容器 <br /><br /> > UAI-Solution:AI解决方案 <br /><br /> > USNAPSHOT:磁盘快照服务 <br /><br /> > ServiceFee:一次性收费 <br /><br /> > UCloudAntiDDoS-NorthChinaBGP:高防-华北BGP <br /><br /> > Cube:容器实例 <br /><br /> > UHybrid-EBN:混合云-企业网 <br /><br /> > UHybrid-VBS:混合云-虚拟边界交换机 <br /><br /> > UHybrid-EBNBandwidth:混合云-企业网带宽 <br /><br /> > UCGS:云游戏 <br /><br /> > USDP:智能大数据平台 <br /><br /> > UIoT-Stack:物联网平台系统套件 <br /><br /> > uiotedgebox:物联网边缘盒子 <br /><br /> > UClickhouse:云数据库仓库UClickHouse <br /><br /> > UDNS:云解析 <br /><br /> > UFS-SMB:SMB文件系统 <br /><br /> > EPC:云极高性能计算节点 <br /><br /> > EPCCluster:高性能计算集群 <br /><br /> > Instance:海外站云主机 <br /><br /> > UGA3:全球动态加速 <br /><br /> > uhybrid_xzone:混合云-金翼XZone <br /><br /> > udts:数据传输服务 <br /><br /> > uk8s_service:容器云 <br /><br /> > UIW:无间盾反欺诈系统 <br /><br /> > ISMS:视频短信 <br /><br /> > PLiveUPRO:Polyv云直播U享版 <br /><br /> > UNVS:号码认证 <br /><br /> > UVMS:语音消息服务 <br /><br /> > UGame:云游戏 <br /><br /> > UHive:UHive <br /><br /> > UDoris:UDoris <br /><br /> > USLK:短链工具 <br /><br /> > UPCA:UPCA <br /><br /> > URCM:富信消息 <br /><br /> > HTTPDNS:HTTP DNS <br /><br /> > UAdsSp:DDOS防御服务包 <br /><br /> > UPhone-eip:云手机（eip） <br /><br /> > UPhone-share-bandwidth:云手机（共享带宽） <br /><br /> > UCloud Phone Server:云手机服务器 <br /><br /> > UMongoDBMember:云数据库 MongoDB UDB 集群内节点成员 <br /><br /> > UPhone-NetworkResource:云手机（网络资源） <br /><br /> > UOL:海外直播加速 <br /><br /> > UDBProxy:云数据库读写分离中间件 <br /><br /> > UDBProxyMember:云数据库读写分离中间件集群内成员 <br /><br /> > UPgSQL:UDB For PgSQL <br /><br /> > UMongoDB:UMongoDB <br /><br /> > UPresto:UPresto <br /><br /> > UDBC:UDBC <br /><br /> > CAAS:CAAS <br /><br /> > UPhone:云手机 <br /><br /> > NVAS:混合云-网络增值服务 <br /><br /> > UNPP:号码隐私保护 <br /><br /> > UNPP:企业名片 <br /><br /> > UMongoDBVirtualMember:云数据库 MongoDB UDB集群内虚拟节点 <br /><br /> > CF-antiddos:CF高防服务 <br /><br /> > UAM:优信 <br /><br /> > UAIModelFactory:人工智能模型工厂 <br /><br /> > UGNBW:云联网带宽包 <br /><br /> > UDAS:数据库自治服务 <br /><br /> > URM:资源迁移 <br /><br /> > UDTS-DI:数据传输服务-数据集成 <br /><br /> > ALB:应用型负载均衡 <br /><br /> > UTrafficPack:共享流量包 <br /><br /> > ULHost:轻量应用云主机 <br /><br /> > UWSCBandwith:UWAN智联-接入带宽包 <br /><br /> > MySQLBackup:MySQL 备份服务 <br /><br /> > SkyMirror:天镜 <br /><br /> > UCustomImage:自定义镜像 <br /><br /> > UDTS-DIS:数据传输服务-数据集成子任务 <br /><br /> > utm:流量镜像 <br /><br /> > NLB:网络型负载均衡 <br /><br /> > ALS:ALB监听器 <br /><br /> > NLS:NLB监听器 <br /><br /> > ARS:ALB服务节点 <br /><br /> > NRS:NLB服务节点 <br /><br /> > UAIM:卡片消息 <br /><br /> > UWSC:UWAN智联 <br /><br /> > LBIP:负载均衡内网IP <br /><br /> > ULogstash:Logstash服务 <br /><br /> > UWCE:UWAN智联-CE客户网关 <br /><br /> > UWSC-Tunnel:UWAN智联-VPN隧道 <br /><br /> > UNDT:网络拨测 <br /><br /> > UHBW:托管带宽包 <br /><br /> > UHNet:托管网络 <br /><br /> > UH-VRrouter:托管虚拟路由器 <br /><br /> > XC:楼内线 <br /><br /> > UModelVerse:模型服务平台 <br /><br /> > ULogstash-Node:Logstash Node服务 <br /><br /> > CloudWatch:云监控 <br /><br /> > UGN:云联网 <br /><br /> > epsrv:终端节点服务 <br /><br /> > ep:终端节点 <br /><br /> > uwcpe:CPE智能网关 <br /><br /> > uwcpetunnel:CPE隧道 <br /><br /> > USCS:安全定制服务 <br /><br /> > UAAA:应用仓库加速 <br /><br /> > ULogService:日志服务 <br /><br /> > UXZONE-GPU:金翼GPU <br /><br /> > UReach:优睿达 <br /><br /> > UPLVR:专线虚拟路由器 <br /><br /> > maxir:云数据仓库MAXIR <br /><br /> > maxirvector:云数据仓库MAXIR向量版 <br /><br /> > UPFS:文件存储UPFS <br /><br /> > UMarketplace:云市场 <br /><br /> > IPRP:IP资源池 <br /><br /> > ExclusiveHosts:包销宿主机 <br /><br /> > RedisReplicate:Redis 从库 <br /><br /> > SecurityCenter:云安全中心 <br /><br /> > PrivateLink:私有链接 <br /><br /> > UMongoDBBackup:MongoDB备份服务 <br /><br /> > TiDBCluster:分布式数据库 TiDB Cluster <br /><br /> > MAXIRDPS:MAXIR DPS <br /><br /> > Label:标签 <br /><br /> > NVAS:混合云网络增值服务 <br /><br /> > UIBUDS:互联网事业部开发服务 <br /><br /> > KafkaGroup:Kafka消费组 <br /><br /> > RLM:实时无损监控告警 <br /><br /> > USG:安全组 <br /><br /> > CF-antiddos:CF高防服务 <br /><br /> > UClickhouseNode:云数据仓库UClickhouse节点 <br /><br /> > HPCExpress:盘柜直达服务 <br /><br /> > UDI:数据智能 <br /><br /> > UMountPoint:文件系统挂载点 <br /><br /> > UPrometheus:托管Prometheus服务 <br /><br /> > AnycastCleanPromotion:全球清洗促销 <br /><br /> > USMC:服务器迁移中心 <br /><br /> > UK8SPod:UK8SPod 类型资源 <br /><br /> > UAS:弹性伸缩 <br /><br /> > Manul:统一存储 <br /><br /> > UDas:分部式应用服务 <br /><br /> > USecLog:安全日志审计 <br /><br /> > UKafkaSinkerNode:Kafka连接器节点 <br /><br /> > IPv6Address:IPv6地址 <br /><br /> > UFlink-Node:Flink实时计算节点 <br /><br /> > UContract:电子合同 <br /><br /> > NAT64:IPv6转换 <br /><br /> > OBJ_TYPE_UDDBAC:UDDB分析节点 <br /><br /> > OBJ_TYPE_SYS_UDISK_SSD:SSD云硬盘系统盘 <br /><br /> > utoken:令牌服务 <br /><br /> > UATP:API测试平台 <br /><br /> > udb_region:跨可用区高可用数据库 <br /><br /> > compshareImage:算力镜像 <br /><br /> > commImage:算力社区镜像 <br /><br /> > MAXIR AI:知识洞察 <br /><br /> > UCNest:算力云巢 <br /><br /> > IPV6 Gateway:IPV6公网网关 <br /><br /> > UCNest ExIP:算力云巢外网IP <br /><br /> > IPV6 Address:IPV6地址 <br /><br /> > UDBProxy RoGroup for MySQL:数据库代理只读组 <br /><br /> > SSD Essential:经济型SSD云盘 <br /><br /> > RSSD Essential:经济型RSSD云盘 <br /><br /> > RocketMQ Message Queue Node:消息队列节点 <br /><br /> > Runc Instance:Runc 实例 <br /><br /> > Runc Image:Runc 镜像 <br /><br /> > UCDC:专属云平台服务 <br /><br /> > Other:其他 |**Yes**|
| **ResourceTypeCode** | int | 产品类型代码 |**Yes**|
| **ItemDetails** | array[[*ItemDetail*](#ItemDetail)] | 产品配置 |**Yes**|
| **ResourceExtendInfo** | array[[*ResourceExtendInfo*](#ResourceExtendInfo)] | 资源标识 |**Yes**|
| **ResourceLabel** | object | 资源标签。字符串键值对的map：{"cs_label": "cs_label_value"} |**Yes**|
| **ShowHover** | int | 订单支付状态。枚举值：<br /><br />> 0:未支付 <br /><br /> > 1:已支付 |**Yes**|
| **UserEmail** | string | 账户邮箱 |**Yes**|
| **UserName** | string | 账户名 |**Yes**|
| **UserDisplayName** | string | 账户昵称 |**Yes**|
| **Admin** | int | 是否为主账号。枚举值：<br /><br /> > 0:子账号 <br /><br /> > 1:主账号 |**Yes**|

#### ItemDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductName** | string | 产品小类名称 |**Yes**|
| **Value** | string | 产品小类规格 |**Yes**|

#### ResourceExtendInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 资源标识健 |**Yes**|
| **Value** | string | 资源标识值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUBillDetail
&BillingCycle= 2022-01,
&ResourceTypes.0= uhost,
&ResourceTypes.1= udisk,
&ProjectName= Default,
&ResourceIds.0= uhost-bzgf1gh5,
&ResourceIds.1= uhost-gu1xpspa,
&OrderType= OT_RENEW,
&ChargeType= Dynamic,
&ShowZero= 0,
&PaidState= 0,
&Limit= 25,
&Offset= 0
```

### 响应示例
    
```json
{
  "Action": "ListUBillDetailResponse",
  "Items": [
    {
      "Admin": 1,
      "Amount": "4.21",
      "AmountCoupon": "0.00",
      "AmountFree": "0.00",
      "AmountReal": "4.21",
      "AzGroupCName": "北京二",
      "ChargeType": "Dynamic",
      "CreateTime": 1643641241,
      "EndTime": 1643644800,
      "ItemDetails": [
        {
          "ProductName": "主机CPU",
          "Value": "4核"
        },
        {
          "ProductName": "主机内存",
          "Value": "16384MB"
        },
        {
          "ProductName": "GPU_P40",
          "Value": "1颗"
        },
        {
          "ProductName": "SSD云盘（系统盘）",
          "Value": "40GB"
        }
      ],
      "OrderNo": "20220131033108259519838",
      "OrderType": "OT_RENEW",
      "ProjectName": "Default",
      "ResourceExtendInfo": [
        {
          "KeyId": "name",
          "Value": "UHost-hl4"
        },
        {
          "KeyId": "private_ip",
          "Value": "10.25.113.204"
        }
      ],
      "ResourceId": "uhost-bzgf1gh5",
      "ResourceType": "uhost",
      "ResourceTypeCode": 1,
      "ShowHover": 1,
      "StartTime": 1643641200,
      "UserDisplayName": "数据学院",
      "UserEmail": "daseucloud@foxmail.com",
      "UserName": "root"
    },
    {
      "Admin": 1,
      "Amount": "4.21",
      "AmountCoupon": "0.00",
      "AmountFree": "0.00",
      "AmountReal": "4.21",
      "AzGroupCName": "北京二",
      "ChargeType": "Dynamic",
      "CreateTime": 1643641239,
      "EndTime": 1643644800,
      "ItemDetails": [
        {
          "ProductName": "主机CPU",
          "Value": "4核"
        },
        {
          "ProductName": "主机内存",
          "Value": "16384MB"
        },
        {
          "ProductName": "GPU_P40",
          "Value": "1颗"
        },
        {
          "ProductName": "SSD云盘（系统盘）",
          "Value": "40GB"
        }
      ],
      "OrderNo": "20220131032808257245615",
      "OrderType": "OT_RENEW",
      "ProjectName": "Default",
      "ResourceExtendInfo": [
        {
          "KeyId": "name",
          "Value": "UHost-hl2"
        },
        {
          "KeyId": "private_ip",
          "Value": "10.25.98.190"
        }
      ],
      "ResourceId": "uhost-gu1xpspa",
      "ResourceType": "uhost",
      "ResourceTypeCode": 1,
      "ShowHover": 1,
      "StartTime": 1643641200,
      "UserDisplayName": "数据学院",
      "UserEmail": "daseucloud@foxmail.com",
      "UserName": "root"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





