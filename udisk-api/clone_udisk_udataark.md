# 从数据方舟的备份创建UDisk - CloneUDiskUDataArk

## 简介

从数据方舟的备份创建UDisk






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CloneUDiskUDataArk)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CloneUDiskUDataArk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 实例名称 |**Yes**|
| **UDiskId** | string | 需要克隆的源盘id |**Yes**|
| **SnapshotTime** | int | 指定从方舟克隆的备份时间点 |**Yes**|
| **Comment** | string | Disk注释 |No|
| **ChargeType** | string | Year , Month, Dynamic，Postpay 默认: Dynamic |No|
| **Quantity** | int | 购买时长 默认: 1 |No|
| **UDataArkMode** | string | 【开启数据方舟入口已关闭】是否开启数据方舟。Yes：开启，No：不开启，默认值：No |No|
| **SnapshotService** | string | 是否开启快照服务（开启快照服务，可免费开启数据方舟）。Yes：开启，No：不开启，默认值：No |No|
| **Size** | int | 新克隆UDisk的大小,单位:GB。指定Size须大于等于源盘Size，小于源盘Size或者不指定该参数均按源盘Size克隆新盘。普通数据盘：范围[1\~8000]；SSD数据盘：范围[1\~8000]；RSSD数据盘：范围[1\~32000]；高效数据盘：范围[1\~32000]。 |No|
| **Tag** | string | 业务组 默认：Default |No|
| **RdmaClusterId** | string | RDMA集群id。指定RSSD云盘克隆到对应的RDMA集群。 |No|
| **HostId** | string | Host实例ID。克隆出的云盘可直接挂载到该主机上。 |No|
| **BackupMode** | string | 快照服务备份策略。默认采用基础版套餐开通，“Base”：基础版，“ Ultimate”：旗舰版，“ Custom”：自定义备份链 |No|
| **Journal** | int | BackupMode为Custom时，进行设置, 以12小时秒级为基础进行倍数扩增，如12、24、36、48 |No|
| **Hour** | int | BackupMode为Custom时，进行设置, 以24小时级为基础进行倍数扩增，如24、48、72、96 |No|
| **Day** | int | BackupMode为Custom时，进行设置, 以5天级为基础进行倍数扩增，如5、10、15、20、25、30 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDiskId** | array[string] | 创建UDisk Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CloneUDiskUDataArk
&Region=cn-east
&Zone=cn-east-01
&UDiskId=F207B59C-BA54-4455-9CF1-996DB5A7CD22
&Name=xxx
&SnapshotTime=1473646985
&Tag=PgHINlLb
&SnapshotService=SbsKvZHb
&RdmaClusterId=fOAYalof
&HostId=qMNVFVUO
&BackupMode=dBoEybTD
&Journal=9
&Hour=2
&Day=9
```

### 响应示例
    
```json
{
  "Action": "CloneUDiskUDataArkResponse",
  "RetCode": 0,
  "UDiskId": "ebi2"
}
```





