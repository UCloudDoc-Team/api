# 获取创建PG云数据库价格 - GetUPgSQLInstancePrice

## 简介

获取创建PG云数据库价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUPgSQLInstancePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPgSQLInstancePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **MachineType** | string | 机器配置类型 参考2C4G机器：o.pgsql2m.medium |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB) |**Yes**|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： Year，按年付费； Month，按月付费； Dynamic，按小时付费（需开启权限）。默认为月付 |No|
| **Quantity** | int | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传0，代表了购买至月末。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UPgSQLInstancePriceSet*](#UPgSQLInstancePriceSet)] | 价格列表 |No|

#### 数据模型


#### UPgSQLInstancePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，Year，Month，Dynamic。 |**Yes**|
| **Price** | float | 实际价格，单位：元，保留小数点后两位有效数字。 |**Yes**|
| **OriginalPrice** | float | 购买原价，单位：元。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPgSQLInstancePrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=sNOPuFhh
&ChargeType=ijAcdkHV
&Quantity=1
&MachineType=cMcdekRq
&DiskSpace=1
&MachineType=reLaNHli
&DiskSpace=2
&InstanceMode=IhlwCzcu
```

### 响应示例
    
```json
{
  "Action": "GetUPgSQLInstancePriceResponse",
  "PriceSet": [
    {
      "ChargeType": "jUAzlxWQ",
      "OriginalPrice": 9.16887,
      "Price": 3.25771
    }
  ],
  "RetCode": 0
}
```





