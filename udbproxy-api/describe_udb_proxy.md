# 获取UDB代理服务详细信息 - DescribeUDBProxy

## 简介

获取UDB代理服务详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBProxy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBProxy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UDBProxyID** | string | 读写分离ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDBProxyID** | string | UDBProxy实例ID |**Yes**|
| **UDBProxyIP** | string | UDB代理服务IP |**Yes**|
| **UDBProxyPort** | int | UDB代理服务端口 |**Yes**|
| **State** | string | 状态 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|
| **ReadWeightMode** | int | 读权重模式:1-主节点模式;2-节点均衡模式;3-从节点均衡(排除主节点);5-用户自定义模式 |**Yes**|
| **CPUCores** | int | cpu核数 |**Yes**|
| **Memory** | int | 内存 |**Yes**|
| **NodeCount** | int | 集群实例节点数 |**Yes**|
| **ZoneId** | int | 可用区id |**Yes**|
| **Name** | string | 名称 |**Yes**|
| **MaxConnection** | int | UDB代理服务最大连接数 |**Yes**|
| **DelayThreshold** | int | 延迟阈值(单位s) |**Yes**|
| **UDBReplicas** | array[[*Replica*](#Replica)] | UDB集群数据 |**Yes**|
| **Nodes** | array[[*Node*](#Node)] | 集群实例服务节点数据 |**Yes**|
| **SQLLimitCount** | int | sql限流数量 |No|
| **SQLRouterCount** | int | sql路由数量 |No|
| **InstanceVersion** | string | 实例版本 |No|
| **EnableTransSplit** | int | 是否启用事务拆分(1：启用事务拆分，2:关闭事务拆分) |No|

#### 数据模型


#### Replica

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 数据库ID |**Yes**|
| **IP** | string | 数据库IP |**Yes**|
| **Port** | int | 数据库服务端口 |**Yes**|
| **ReadWeight** | int | 读权重 |**Yes**|
| **State** | string | 状态 |**Yes**|
| **Role** | string | 角色[master-主库，slave-从库] |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|
| **JoinState** | boolean | 是否加入代理服务(true:加入，false:未加入) |**Yes**|
| **Name** | string | 数据库名称 |**Yes**|

#### Node

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 服务节点id |**Yes**|
| **State** | string | 服务节点状态 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBProxy
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DAIoycmE
&UDBProxyID=nCNBolTi
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBProxyResponse",
  "CPUCores": 3,
  "CreateTime": 8,
  "DelayThreshold": 4,
  "EnableTransSplit": 3,
  "InstanceVersion": "aqshAbAK",
  "MaxConnection": 7,
  "Memory": 2,
  "ModifyTime": 5,
  "Name": "OlLESJIS",
  "NodeCount": 9,
  "Nodes": [
    {
      "ID": "ttlkSuYX",
      "State": "FZHOtjjk"
    }
  ],
  "ReadWeightMode": 8,
  "RetCode": 0,
  "SQLLimitCount": 2,
  "SQLRouterCount": 3,
  "State": "mHFdpsGC",
  "UDBProxyID": "GkfnbTgu",
  "UDBProxyIP": "wtaQVqRN",
  "UDBProxyPort": 8,
  "UDBReplicas": [
    {
      "CreateTime": 1,
      "ID": "tBnNCgQT",
      "IP": "GhlRZTad",
      "JoinState": "rrshQjQh",
      "ModifyTime": 3,
      "Port": 4,
      "ReadWeight": 50,
      "Role": "hHQYuZQH",
      "State": "pdIdZPxx"
    }
  ],
  "ZoneId": "ObOfZhoE"
}
```





