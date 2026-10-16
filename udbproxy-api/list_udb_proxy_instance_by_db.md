# 查询DB启用代理数据 - ListUDBProxyInstanceByDB

## 简介

查询DB启用代理数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDBProxyInstanceByDB)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDBProxyInstanceByDB`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DBID** | string | 数据库DB资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDBProxyBaseItems** | array[[*UDBProxyBaseItem*](#UDBProxyBaseItem)] | 代理列表数据 |**Yes**|

#### 数据模型


#### UDBProxyBaseItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ReadWeightMode** | int | 读权重模式:1-主节点模式;2-节点均衡模式;3-从节点均衡(排除主节点);5-用户自定义模式 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ID** | string | 代理ID |No|
| **IP** | string | 代理IP |No|
| **Port** | int | 代理端口 |No|
| **State** | string | 状态 |No|
| **ZoneID** | int | 可用区ID |No|
| **NodeCount** | int | 代理节点数 |No|
| **CPUCores** | int | 单个代理节点CPU核数 |No|
| **Memory** | int | 单个代理内存 |No|
| **Name** | string | 代理名称 |No|
| **InstanceVersion** | string | 实例版本 |No|
| **BaseDBDataArr** | array[[*BaseDBData*](#BaseDBData)] | 加入代理DB信息 |No|

#### BaseDBData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 数据库ID |No|
| **Name** | string | 数据库名称 |No|
| **ReadWeight** | int | 权重 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDBProxyInstanceByDB
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=pMvbaLux
&DBID=oWYGOumG
```

### 响应示例
    
```json
{
  "Action": "ListUDBProxyInstanceByDBResponse",
  "Message": "hFtwEdKH",
  "RetCode": 0,
  "UDBProxyBaseItems": [
    {
      "BaseDBDataArr": [
        {
          "ID": "tjQuxzNn",
          "Name": "JoGfYcoz",
          "ReadWeight": 6
        }
      ],
      "CPUCores": 1,
      "CreateTime": 3,
      "ID": "exvunmky",
      "IP": "CNFZwvQo",
      "Memory": 1,
      "Name": "hzuxSAHL",
      "NodeCount": 6,
      "Port": 5,
      "ReadWeightMode": 3,
      "State": "whpILLzn",
      "ZoneID": 7
    }
  ]
}
```





