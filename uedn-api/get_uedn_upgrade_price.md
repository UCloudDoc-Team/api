# 获取节点调整差价 - GetUEdnUpgradePrice

## 简介

获取节点调整差价





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUEdnUpgradePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEdnUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **NodeId** | string | 节点ID |**Yes**|
| **CpuCore** | int | cpu核心数 |No|
| **MemSize** | int | 内存大小，单位GB |No|
| **SysDiskSize** | int | 系统盘大小，单位GB |No|
| **DiskSize** | int | 数据盘大小，单位GB |No|
| **NetLimit** | int | 节点带宽限制，单位Mbs |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 规格调整差价 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEdnUpgradePrice
&ProjectId=WpNYPaff
&NodeId=bDOTSYGZ
&CpuCore=5
&MemSize=6
&SysDiskSize=3
&DiskSize=9
&NetLimit=3
```

### 响应示例
    
```json
{
  "Action": "GetUEdnUpgradePriceResponse",
  "Price": 5,
  "RetCode": 0
}
```





