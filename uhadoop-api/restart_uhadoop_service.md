# 重启集群服务（包含start|stop|restart） - RestartUHadoopService

## 简介

重启集群服务（包含start\|stop\|restart）

?> var states = {<br />    Unknown: 0, // 为止， 与1同样处理即可<br />    Running: 1,      //启用<br />    Stopped: 2,      //停用<br />    Starting: 3,     //启用中 <br />    Stopping: 4,     //停用中 <br />    Start_failed: 5,  //启用异常 <br />    Stop_failed: 6    //停用异常 <br />}




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=RestartUHadoopService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RestartUHadoopService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ServiceName** | string | 要操作的服务名。可通过ListUHadoopFrameworkApp接口获取 |**Yes**|
| **InstanceId** | string | 实例ID |**Yes**|
| **ApplicationVersion** | string | 应用版本，ApplicationVersion传参时，表示这次操作是整个应用所有服务。 |No|
| **OnlyStart** | boolean | 只启动。值为false\|true之一，默认false，当OnlyStart和OnlyStop同时置为true，则重启。 |No|
| **OnlyStop** | boolean | 只停止。值为false\|true之一，默认false。当OnlyStart和OnlyStop同时置为true，则重启。 |No|
| **NodeId.N** | string | 要操作的NodeId数组。如果传入，则用于过滤操作哪些Node。 |No|
| **NodeRole.N** | string | 要操作的NodeRole数组。如果传入，则用于过滤操作哪些Node。值为以下之一<br />master\|core\|task |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **State** | string | 当前执行状态，running(操作运行中)\|success(操作成功)\|failed(操作失败)\|killed(操作被终止)。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RestartUHadoopService
&Region=YAnCBcjk
&Zone=GvehZWYc
&ClusterInstanceId=bbUCSBRs
&ServiceName=TDsLdPVn
&OnlyStart=2
&OnlyStop=5
&NodeId.n=UOtEpVtZ
&NodeRole.n=FhCFvHhj
&ApplicationVersion=fLUiqzev
&ApplicationVersion=TYSoXwIp
```

### 响应示例
    
```json
{
  "Action": "RestartUHadoopServiceResponse",
  "Message": "hZnmwFKc",
  "RetCode": 0
}
```





