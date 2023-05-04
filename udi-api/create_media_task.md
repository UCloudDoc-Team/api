# 创建媒体任务 - CreateMediaTask

## 简介

创建一个多媒体任务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateMediaTask)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateMediaTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **StorageBackend** | string | 存储源 |**Yes**|
| **Bucket** | string | Bucket名称 |**Yes**|
| **SrcKey** | string | 源文件 |**Yes**|
| **DstKey** | string | 目标生成文件 |**Yes**|
| **Function** | string | 功能名称：例VideoTranscode |**Yes**|
| **FunctionParamTemplateId** | string | 功能的参数模板ID，需要事先创建模板才可用，也可以使用预设模板，详细可通过DescribeFunctionTemplate接口查询 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskId** | string | 任务ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateMediaTask
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tzatoIXH
&StorageBackend=YoFitIHj
&StorageParams=PqjeNNpw
&Function=LHqJjqaZ
&FunctionParams=mIEoPnPL
&FunctionParamTemplateId=plnWCdEC
&SrcKey=hxnAKiaD
&Function=rXstzpPs
&SrcKey=iRJccJBm
&Function=GCLpwisf
```

### 响应示例
    
```json
{
  "Action": "CreateMediaTaskResponse",
  "ErrMsg": "JlmdPwKW",
  "RetCode": 0,
  "TaskId": "owVuAaZp"
}
```





