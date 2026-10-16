# 拉取预付费实例列表 - ListTiDBClusterService

## 简介

拉取预付费实例列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListTiDBClusterService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListTiDBClusterService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*UTiDBServiceData*](#UTiDBServiceData)] | 集群列表 |**Yes**|

#### 数据模型


#### UTiDBServiceData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GrafanaUrl** | string | grafana地址 |No|
| **Id** | string | 集群ID |No|
| **Name** | string | 集群名称 |No|
| **Ip** | string | 集群ip |No|
| **Port** | int | 集群端口 |No|
| **State** | string | 集群状态 |No|
| **TiFlashState** | string | 集群TiFlash服务状态 |No|
| **BinlogState** | string | 集群Binlog服务状态 |No|
| **AutoBackup** | string | 自动备份状态 |No|
| **VPCId** | string | 私有网Id |No|
| **SubnetId** | string | 子网ID |No|
| **Version** | string | 集群版本 |No|
| **DTType** | int | 容灾类型 |No|
| **DashboardUrl** | string | Dashboard地址 |No|
| **CreateTime** | int | 创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListTiDBClusterService
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=yNdiFPfB
&Offset=4
&Limit=6
```

### 响应示例
    
```json
{
  "Action": "ListTiDBClusterServiceResponse",
  "Data": [
    {
      "AutoBackup": "mYpOpBwW",
      "BinlogState": "DhcjgMvN",
      "CreateTime": 9,
      "DTType": 8,
      "DashboardUrl": "iNAmJurL",
      "Id": "WrrLtFEh",
      "Ip": "jkVbOGHH",
      "Name": "CaCDOsFn",
      "Port": 1,
      "State": "KwiEfmef",
      "SubnetId": "wfMYQsER",
      "TiFlashState": "aVNWVmAC",
      "VPCId": "oOLPFaYf",
      "Version": "GdOnpkKh"
    }
  ],
  "RetCode": 0
}
```





