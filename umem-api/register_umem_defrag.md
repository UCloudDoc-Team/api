# 动态开关redis碎片整理选项 - RegisterUMemDefrag

## 简介

动态开关redis碎片整理选项






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=RegisterUMemDefrag)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RegisterUMemDefrag`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **StartTime** | int | 开始时间戳 |No|
| **EndTime** | int | 关闭时间戳 |No|
| **OperateType** | string | 操作类型：<br />“Once”： 表示单次执行， <br />“Open”：表示开启策略<br />“Close”:  表示关闭策略（分布式实例只支持Once）。 |No|
| **FragTime** | int | 任务时间周期，单位为分钟。 |No|
| **FragSize** | int | 碎片整理阈值，范围为 100-200（分布式实例该参数无效）。 |No|
| **StartHour** | int | 开始整点数值（分布式实例该参数无效）。 |No|
| **StartMin** | int | 开始分钟数（分布式实例该参数无效）。 |No|
| **EndHour** | int | 结束整点数值（分布式实例该参数无效）。 |No|
| **EndMin** | int | 结束分钟数（分布式实例该参数无效）。 |No|
| **IsUnion** | boolean | AND逻辑字段，表示 阈值和时间段都满足（分布式实例该参数无效）。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RegisterUMemDefrag
&Region=cn-zj
&Zone=cn-zj-01
&ResourceId=KjIbMAJE
&OperateType=XgXNHDkJ
&OperateCycle=pzPrIRzl
&StartTime=2
&EndTime=2
&OperateType=zcMGnRxQ
&FragTime=1
&FragRatio=7.94436
&StartHour=4
&StartMin=5
&EndHour=9
&EndMin=1
&OperateType=LPmokZrJ
&FragTime=9
&FragRatio=3.48218
&StartHour=9
&StartMin=3
&EndHour=8
&EndMin=8
&IsUnion=false
```

### 响应示例
    
```json
{
  "Action": "RegisterUMemDefragResponse",
  "RetCode": 0
}
```





