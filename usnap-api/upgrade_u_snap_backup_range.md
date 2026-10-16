# 调整备份链范围 - UpgradeUSnapBackupRange

## 简介

调整备份链范围









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpgradeUSnapBackupRange`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VDiskId** | string | 磁盘ID |**Yes**|
| **Size** | int | 磁盘大小 |**Yes**|
| **BackupMode** | int | 默认采用入门级套餐开通，“ Primer”：入门版，“Base”：基础版，“ Enterprise”：企业版，“ Ultimate”：旗舰版，“ Custom”：自定义备份链 |**Yes**|
| **SnapshotSvcId** | string | 快照服务ID |No|
| **Journal** | int | BackupMode为Custom时，进行设置, 以12小时秒级为基础进行倍数扩增，如12、24、36、48 |No|
| **Hour** | int | BackupMode为Custom时，进行设置, 以24小时级为基础进行倍数扩增，如24、48、72、96<br /> |No|
| **Day** | int | BackupMode为Custom时，进行设置, 以5天级为基础进行倍数扩增，如5、10、15、20、25、30<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpgradeUSnapBackupRange
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=Fqlinzjf
&VDiskId=DFSpnovI
&Form=2
&Journal=6
&Hour=8
&Day=5
&Size=2
&VDiskId=NORuxjEi
&VDiskId=uMNPqDmK
&VDiskId=yrYQOOyK
```

### 响应示例
    
```json
{
  "Action": "UpgradeUSnapBackupRangeResponse",
  "RetCode": 0
}
```





