# 查询代理客户端连接IP信息(实时） - ListUDBProxyClient

## 简介

查询代理客户端连接IP信息(实时）

?> 当前接口仅仅支持与2023年3月10日后创建的代理支持




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDBProxyClient)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDBProxyClient`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UDBProxyID** | string | 代理ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UDBProxyID** | string | 代理ID |**Yes**|
| **NodeClientInfos** | array[[*NodeClientInfo*](#NodeClientInfo)] | 代理节点客户端IP连接信息 |**Yes**|

#### 数据模型


#### NodeClientInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Records** | array[[*ProxyProcesslist*](#ProxyProcesslist)] | 客户端IP连接信息 |No|
| **ID** | string | 代理节点ID |No|
| **IP** | string | 代理节点IP |No|

#### ProxyProcesslist

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | 当前连接DB进程ID |No|
| **User** | string | 启动这个线程的用户 |No|
| **Host** | string | 代理连接DB地址 |No|
| **DB** | string | 当前执行的命令是在哪一个数据库上。如果没有指定数据库，则该值为 NULL |No|
| **Command** | string | 显示当前连接的执行的命令 |No|
| **Time** | int | 表示该线程处于当前状态的时间 |No|
| **State** | string | 线程的状态，和 Command 对应 |No|
| **Info** | string | 一般记录的是线程执行的语句 |No|
| **ClientHost** | string | 客户端来源IP地址 |No|
| **DBID** | string | 数据库资源ID |No|
| **Role** | string | 数据库角色(主库/从库) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDBProxyClient
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jgfkYodX
&UDBProxyID=DYvlHomp
```

### 响应示例
    
```json
{
  "Action": "ListUDBProxyClientResponse",
  "NodeClientInfos": [
    {
      "ID": "XMzPaFXa",
      "IP": "FKtUfzpg",
      "Records": [
        {
          "Count": 5,
          "IP": "GUjJGHGa"
        }
      ]
    }
  ],
  "RetCode": 0,
  "UDBProxyID": "LTXRBQLw"
}
```





