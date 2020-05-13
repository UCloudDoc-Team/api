# 获取资源支持监控指标信息 - DescribeResourceMetric

## 简介

获取资源支持监控指标信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeResourceMetric)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeResourceMetric`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 资源类型 支持如下类型：<br />dbaudit：数据库审计；<br />docker:容器服务；<br />docker_node:容器服务节点；<br />eip：弹性IP；<br />fortress:堡垒机；<br />hybridcloud_lan:混合云局域网；<br />hybridcloud_port:混合云交换机端口；<br />hybridcloud_port_sum:混合云外网总出口；<br />mq：消息队列；<br />natgw：NAT网关；<br />phost：物理云主机；<br />sharebandwidth：共享带宽；<br />uaiservice：AI在线服务；<br />ucdn：云分发；<br />udb：云数据库；<br />uddb：分布式数据库；<br />uddbac：UDDB分析节点；<br />uddbmd：分布式数据库中间件；<br />uddbnode：分布式数据库节点；<br />udisk：云硬盘；<br />udisk_rssd：RSSD云硬盘；<br />udisk_ssd：SSD云硬盘（数据盘）；<br />udisk_sys：普通云硬盘（系统盘）；<br />udpn：高速通道；<br />udset:私有专区资源池；<br />udset_uhost:资源池主机；<br />udw：云数据仓库；<br />udw_node:云数据仓库节点；<br />ues：ES服务；<br />ues_node：elasticsearch服务节点；<br />ufile：对象存储；<br />ufs：文件存储；<br />ugaa：全球动态加速；<br />ugc：通用计算；<br />uhadoop：托管Hadoop集群；<br />uhadoop_host：托管Hadoop集群；<br />uhost：云主机；<br />ukafka：Kafka消息队列；<br />ukafka_host：分布式消息节点；<br />ukv：容量型KV存储；<br />ulb：负载均衡；<br />ulb-server：真实服务节点；<br />ulb-vserver：虚拟服务节点；<br />umem：云内存存储；<br />umemcache：单机版memcache；<br />upath：加速线路；<br />uredis：云内存存储；<br />utsdb：时序数据库；<br />vpntunnel：vpn隧道；<br />vserver：虚拟服务节点；<br /><br />各产品支持监控项，请查看：https://docs.ucloud.cn/api/umon-api/get_metric |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*DescribeResourceMetricResponse*](#DescribeResourceMetricResponse)] | 指标信息集合 |**Yes**|

#### 数据模型


#### DescribeResourceMetricResponse

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Unit** | string | 单位：<br />bit Byte Kb KB Mb MB Gb GB Tb TB Pb PB Eb EB iops bps Bps Kbps KBps Mbps MBps Gbps GBps Tbps TBps 个 个/s 次 次/s 千次/s 万次/s % s ms us bool ‱ 个/min 个/核 个/10s bytes/10s MB/s dbm min |**Yes**|
| **ConversionFactor** | int | 保留字段 |**Yes**|
| **Type** | int | 指标类型（暂时没有意义） |**Yes**|
| **MetricGroup** | string | 监控指标组 |**Yes**|
| **SupportAlarm** | string | 是否支持告警：Yes\|No |**Yes**|
| **AlarmRange** | string | 告警阈值设置的有效范围 |**Yes**|
| **Frequency** | int | 告警频率 |**Yes**|
| **MetricId** | int | 监控项id |**Yes**|
| **CompareOption** | array[string] | 比较方法：GE大于等于\|LE小于等于 |**Yes**|
| **MetricName** | string | 指标名字 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeResourceMetric
&ResourceType=uhost
```

### 响应示例
    
```json
{
  "Action": "DescribeResourceMetricResponse",
  "DataSet": [
    {
      "AlarmRange": {
        "max": 100,
        "min": 50
      },
      "CompareOption": [
        "GE"
      ],
      "ConversionFactor": 0,
      "Frequency": 60,
      "MetricGroup": "",
      "MetricId": 8000,
      "MetricName": "CPUUtilization",
      "SupportAlarm": "Yes",
      "Type": "Number",
      "Unit": "%"
    }
  ],
  "RetCode": 0
}
```





