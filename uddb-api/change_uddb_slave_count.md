# 改变分布式数据库数据节点的只读实例个数 - ChangeUDDBSlaveCount

## 简介

改变分布式数据库数据节点的只读实例个数<br />每一个UDDB的数据节点负责处理所有的写入请求。与此同时，每一个数据节点可以配置若干个该节点的只读实例。当主节点的数据写入完毕后，只读实例把这次的写入操作进行更新，从而和数据节点保持一致。<br />只读实例可以使得数据由多份复制，在数据节点和只读实例之间，可以做请求的读写分离, 也就是说, 主节点写入数据之后, 数据的读操作可以由数据只读实例进行分担, 这样减少主节点的压力, 增加性能<br />当改变了数据节点的只读实例个数之后，对于现有的和以后的每一个数据节点都采用这个配置。如果UDDB实例有现有的数据节点, 那么它会根据新配置的参数，自动创建或删除数据节点的只读实例<br />如下状态的UDDB实例可以进行这个操作:<br />Running: 系统正常运行中<br />当请求返回成功之后，UDDB实例的状态变成"ChangingSlaveCount"; 如果返回失败, UDDB实例状态保持不变 当UDDB更改数据分区的只读实例个数成功之后, UDDB实例的状态变成"Running"(正常运行中); 如果更改过程中出现异常, 状态变成"Abnormal"(异常运行中)或者"Error"(运行错误)






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ChangeUDDBSlaveCount)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ChangeUDDBSlaveCount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)<br /> |**Yes**|
| **UDDBId** | string | UDDB资源id |**Yes**|
| **SlaveCount** | string | 每个数据节点的只读实例个数, 取值必须>=0 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ChangeUDDBSlaveCount
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=QCIvSqYb
&DataNodeSlaveCount=tBKPsXCS
&ProjectId=pnUVjMHA
```

### 响应示例
    
```json
{
  "Action": "ChangeUDDBSlaveCountResponse",
  "RetCode": 0
}
```





