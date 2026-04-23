# 列举可选app - ListUHadoopFrameworkApp

## 简介

列举可选app






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUHadoopFrameworkApp)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUHadoopFrameworkApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Framework** | string | 框架，值为'Hadoop'\|'HDFS'\|'MR'\|'StarRocks'之一,框架，例如Hadoop\|MR\|HDFS\|StarRocks Hadoop框架包含存储与计算服务 MR集群包含计算服务 HDFS只包含存储服务,StarRocks为StarRocks集群 |**Yes**|
| **InstanceId** | string | 实例ID,可选。传的话，过滤出适合此集群的app信息。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AppConfigSet** | array[[*AppConfigSet*](#AppConfigSet)] | 应用配置详情 |No|

#### 数据模型


#### AppConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 需要安装的应用如：Hive,HBase, Spark,Hue,Pig等其他组件 |No|
| **AppVersion** | string | 应用的版本号(0.13.1,0.98.6 等等) |No|
| **AppStatus** | string | 应用的状态(运行中)'Running'｜(已停止)'Stopped'｜(启动中)'Starting'｜(停止中)'Stopping'\|(启动失败)'StartFailed'\|(停止失败)'StopFailed'\|(安装中)'Installing'\|(安装失败)'InstallFailed'\|(未安装)'NotInstalled',    <br /> |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUHadoopFrameworkApp
&Region=lhAZpABz
&Zone=nybZjuSm
&UDDPFramework=EcjAkZUH
&ClusterInstanceId=iJSkZtvD
```

### 响应示例
    
```json
{
  "Action": "ListUHadoopFrameworkAppResponse",
  "AppConfigSet": [
    {
      "AppName": "IpixxDeX",
      "AppType": "Basic",
      "AppVersion": "JPpbVbNI"
    },
    {
      "AppName": "QwGuLRQX",
      "AppType": "Basic",
      "AppVersion": "AsAfeSau"
    },
    {
      "AppName": "BCrvwnfu",
      "AppType": "Basic",
      "AppVersion": "PEHJIBGP"
    },
    {
      "AppName": "bpNSfBbp",
      "AppType": "Basic",
      "AppVersion": "MvavmKUA"
    },
    {
      "AppName": "pQFXQkre",
      "AppType": "Basic",
      "AppVersion": "WRsseBXG"
    },
    {
      "AppName": "JajLdFcM",
      "AppType": "Basic",
      "AppVersion": "VuWcLzjS"
    },
    {
      "AppName": "kEvBHwwD",
      "AppType": "Basic",
      "AppVersion": "dVSPONku"
    },
    {
      "AppName": "BKaMVneS",
      "AppType": "Basic",
      "AppVersion": "BmwkCopg"
    }
  ],
  "Message": "JdjIHnVz",
  "RetCode": 0
}
```





