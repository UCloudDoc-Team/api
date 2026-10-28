# 获取 UK8S CNI 节点信息 - GetUK8SCNINodeInfo

## 简介

获取 UK8S 集群各节点的 CNI 版本、状态及版本同步情况。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SCNINodeInfo`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，可选。 |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | UK8S 集群 ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeInfoSet** | array[[*NodePluginInfo*](#NodePluginInfo)] | 节点 CNI 信息列表 |No|
| **DataSource** | string | 数据来源：database 表示数据库记录，ipamd_http 表示通过 ipamd 实时查询。 |No|
| **Partial** | boolean | 是否存在部分节点实时查询失败 |No|
| **HighestVersion** | string | 节点中的最高有效 CNI 版本 |No|
| **AllNodesSynced** | boolean | 是否所有节点实时查询成功且 CNI 版本一致。数据来源为 database 时返回 false。 |No|

#### 数据模型


#### NodePluginInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Node** | string | Node节点名称 |**Yes**|
| **Version** | string | 插件版本 |No|
| **Status** | int | 插件工作状态，0：未知，1：正常，<br />2：异常, 3: 升级中 |No|
| **UpdateTime** | int | 插件信息更新时间 |No|
| **OperationResult** | int | 上次插件操作结果，0：没有上次操作结果，或当前正在执行升级或查询 1：获取成功 2 获取失败  3 升级成功 4 升级失败 |No|
| **IP** | string | Node节点IP |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SCNINodeInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=vlkPRhhO
&ClusterId=CKXpkgnw
&ClusterId=LyhqvKKN
```

### 响应示例
    
```json
{
  "Action": "GetUK8SCNINodeInfoResponse",
  "RetCode": 0
}
```





