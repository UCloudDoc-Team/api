# 创建训练数据集 - CreateUFData

## 简介

创建训练数据集






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUFData`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 名称 |**Yes**|
| **Describe** | string | 描述 |**Yes**|
| **DataSourceType** | string | 数据源类型 |**Yes**|
| **S3Uri** | string | s3地址 |**Yes**|
| **S3Bucket** | string | s3 bucket名 |**Yes**|
| **S3Path** | string | s3路径 |**Yes**|
| **S3AccessKeyID** | string | s3公钥 |**Yes**|
| **S3SecretAccessKey** | string | s3私钥 |**Yes**|
| **Property** | string | 文件类型：File\|Directory |No|
| **DataType** | string | 数据类型Text\|Image\|Audio\|Video |No|
| **Formatting** | string | 数据格式：alpaca\|sharegpt |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*CreateDataResponseData*](#CreateDataResponseData) | 响应数据体 |**Yes**|

#### 数据模型


#### CreateDataResponseData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 主键Id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUFData
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XoWgRSDS
&Name=brFaHAmz
&Describe=dqJlYfLC
&DataSourceType=VdqfPOYk
&S3Uri=bFOQSMGT
&S3Bucket=zVIBhvDH
&S3Path=LXeVlzlt
&S3AccessKeyID=vJmZpysF
&S3SecretAccessKey=TbckXMxb
&Property=MgbVJyDi
&DataType=tsGjKAma
&Formatting=tjVvaCLc
```

### 响应示例
    
```json
{
  "Action": "CreateUFDataResponse",
  "Id": "dNMXynUW",
  "RetCode": 0
}
```





