# 获取裸金属机型的详细信息 - DescribeBaremetalMachineType

## 简介

获取裸金属机型的详细描述信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBaremetalMachineType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBaremetalMachineType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | string | 具体机型。若不填写，则返回全部机型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MachineTypes** | array[[*PHostCloudMachineTypeSet*](#PHostCloudMachineTypeSet)] | 机型列表，模型：PHostCloudMachineTypeSet |No|

#### 数据模型


#### PHostCloudMachineTypeSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 物理云主机机型别名，全网唯一。 |**Yes**|
| **CPU** | [*PHostCPUSet*](#PHostCPUSet) | CPU信息 |No|
| **Memory** | int | 内存大小，单位MB |No|
| **Components** | [*PHostComponentSet*](#PHostComponentSet) | 其他组件信息<br /> |No|
| **Clusters** | array[[*PHostClusterSet*](#PHostClusterSet)] | 集群库存信息 |No|

#### PHostCPUSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Model** | string | CPU型号 |No|
| **Frequence** | string | CPU主频 |No|
| **Count** | int | CPU个数 |No|
| **CoreCount** | int | CPU核数 |No|

#### PHostComponentSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 组件名称 |No|
| **Count** | int | 组件数量 |No|

#### PHostClusterSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 集群名。枚举值：千兆网络集群：1G；万兆网络集群：10G；智能网卡网络：25G； |No|
| **StockStatus** | string | 库存状态。枚举值：有库存：Available；无库存：SoldOut |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeBaremetalMachineType
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DjVQZCeC
&Type=YOdfvZKs
```

### 响应示例
    
```json
{
  "Action": "DescribeBaremetalMachineTypeResponse",
  "MachineTypes": "wLDjOaIJ",
  "RetCode": 0
}
```





