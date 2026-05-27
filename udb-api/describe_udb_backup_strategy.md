# 获取实例备份策略 - DescribeUDBBackupStrategy

## 简介

获取实例备份策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBBackupStrategy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBBackupStrategy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DBId** | string | 实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackupBeginTime** | int | 备份策略，不可修改，开始时间，单位小时计，默认3点 |**Yes**|
| **BackupDate** | string | 备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能<br /> |**Yes**|
| **BackupMethod** | string | 默认的备份方式，nobackup表示不备份， snapshot 表示使用快照备份，logic 表示使用逻辑备份，xtrabackup表示使用物理备份。ark_snapshot 方舟快照备份 |**Yes**|
| **UserUFileData** | [*UFileDataSet*](#UFileDataSet) | 用户转存备份到自己的UFILE配置, 结构参考UFileDataSet<br /> |**Yes**|
| **SaveDays** | int | 保留多少天 |**Yes**|

#### 数据模型


#### UFileDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TokenID** | string | Ufile的令牌tokenid |No|
| **Bucket** | string | bucket名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBBackupStrategy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tCgFGEsW
&DBId=FxcIQFbp
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBBackupStrategyResponse",
  "BackupBeginTime": 2,
  "BackupDate": "chybncZG",
  "BackupMethod": "csrcwruP",
  "RetCode": 0,
  "SaveDays": 6,
  "UserUFileData": {}
}
```





