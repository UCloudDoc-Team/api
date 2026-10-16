# 日志打包列表 - ListUMongoDBLogPackage

## 简介

日志打包列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMongoDBLogPackage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMongoDBLogPackage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群id |**Yes**|
| **NodeId** | string | 节点id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*PackageInfo*](#PackageInfo)] | 列表 |**Yes**|

#### 数据模型


#### PackageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | id |No|
| **Name** | string | 名称 |No|
| **State** | string | Package_Running,Package_Success,Package_Failed,Package_Deleting,Package_Deleted,Package_DeleteFailed |No|
| **Size** | int | 大小,单位字节 |No|
| **PackageType** | string | SlowLog,ErrorLog |No|
| **ClusterId** | string | 集群id |No|
| **NodeId** | string | 节点id |No|
| **Role** | string | 角色 |No|
| **Begin** | int | 开始时间 |No|
| **End** | int | 结束时间 |No|
| **CreateTime** | int | 创建时间 |No|
| **FinishTime** | int | 完成时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMongoDBLogPackage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cCrrDBep
&ClusterId=afqpXrft
&NodeId=zLejAepe
```

### 响应示例
    
```json
{
  "Action": "ListUMongoDBLogPackageResponse",
  "DataSet": [
    {
      "Begin": 5,
      "ClusterId": "uzRxRBKy",
      "CreateTime": 5,
      "End": 1,
      "FinishTime": 1,
      "Id": 6,
      "Name": "lplwcWTx",
      "NodeId": "JnetkalK",
      "PackageType": "TaRJoULs",
      "Size": 2,
      "State": "kkpjvQUt"
    }
  ],
  "RetCode": 0
}
```





