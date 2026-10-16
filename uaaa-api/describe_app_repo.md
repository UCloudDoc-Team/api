# 查询应用仓库实例信息 - DescribeAppRepo

## 简介

查询应用仓库实例信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeAppRepo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAppRepo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 应用仓库加速实例ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*AppRepoInstance*](#AppRepoInstance)] | 应用仓库实例列表 |No|

#### 数据模型


#### AppRepoInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VPC** | array[string] | 应用仓库绑定的vpc 信息 |**Yes**|
| **RecordName** | array[string] | 应用仓库绑定的加速域名 |**Yes**|
| **InstanceId** | string | 应用仓库实例ID |**Yes**|
| **Name** | string | 应用仓库名 |**Yes**|
| **ChargeType** | string | 计费类型 |**Yes**|
| **Description** | string | 应用仓库描述信息 |**Yes**|
| **CreateTime** | int | 创建时间。格式为Unix Timestamp |**Yes**|
| **ExpireTime** | int | 到期时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAppRepo
&Region=cn-bj2
&ProjectId=org-XXXX
&InstanceId=uaaa-XXXX
```

### 响应示例
    
```json
{
  "Action": "DescribeAppRepoResponse",
  "DataSet": [
    {
      "ChargeType": "Dynamic",
      "CreateTime": 1729496374,
      "Description": "",
      "ExpireTime": 1734678000,
      "InstanceId": "uaaa-XXXXXXXX",
      "Name": "23",
      "RecordName": [
        "*.docker.com",
        "*.gcr.io",
        "*.k8s.io",
        "*.nvidia.com"
      ],
      "VPC": [
        "uvnet-XXXXX"
      ]
    }
  ],
  "Message": "Success",
  "RetCode": 0
}
```





