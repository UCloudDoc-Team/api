# 获取磁盘快照服务价格 - DescribeSnapshotServicePrice

## 简介

获取磁盘快照服务实例价格信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSnapshotServicePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 磁盘大小 |**Yes**|
| **ChargeType** | string | Year , Month, Dynamic 默认: Month |No|
| **Quantity** | int | 购买服务时长，默认值是1 |No|
| **BackupMode** | string | 默认采用入门级套餐开通，“ Primer”：入门版，“Base”：基础版，“ Enterprise”：企业版，“ Ultimate”：旗舰版，“ Custom”：自定义备份链 |No|
| **Journal** | int | BackupMode为Custom时，进行设置, 以12小时秒级为基础进行倍数扩增，如12、24、36、48 |No|
| **Hour** | int | BackupMode为Custom时，进行设置, 以24小时级为基础进行倍数扩增，如24、48、72、96 |No|
| **Day** | int | BackupMode为Custom时，进行设置, 以5天级为基础进行倍数扩增，如5、10、15、20、25、30 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | [*SnapshotServicePriceDataSet*](#SnapshotServicePriceDataSet) | 价格参数列表，具体说明见SnapshotServicePriceDataSet |No|

#### 数据模型


#### SnapshotServicePriceDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year， Month， Dynamic |No|
| **Price** | int | 实际价格 (单位: 分) |No|
| **OriginalPrice** | int | 用户折后价(对应计费CustomPrice) |No|
| **ListPrice** | int | 原价(对应计费OriginalPrice) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSnapshotServicePrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=YYkcnwog
&VDiskId=vDRTnYEK
&ChargeType=TcmcJLby
&Quantity=fqNBRpVA
&BackupMode=IcQFSHJJ
&Journal=7
&Hour=9
&Day=2
```

### 响应示例
    
```json
{
  "Action": "DescribeSnapshotServicePriceResponse",
  "DataSet": "XsAPerJm",
  "RetCode": 0
}
```





