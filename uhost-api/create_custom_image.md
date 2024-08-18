# 创建自制镜像 - CreateCustomImage

## 简介

从指定UHost实例，生成自定义镜像。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCustomImage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCustomImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|
| **ImageName** | string | 镜像名称 |**Yes**|
| **ImageDescription** | string | 镜像描述 |No|
| **DataUDiskIds.N** | string | 【数组】关联的云盘数据盘id列表。注意: 云盘数据盘需要开启快照服务 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageId** | string | 镜像Id |No|
| **DataSnapshotIds** | array[string] | 云盘数据盘快照id列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCustomImage
&Region=cn-bj2
&ProjectId=org-xxx
&UHostId=uhost-xxx
&ImageName=Test
&DataUDiskIds.N=TtzKXtvV
```

### 响应示例
    
```json
{
  "Action": "CreateCustomImageResponse",
  "DataSnapshotIds": [
    "hoSgBxwr"
  ],
  "ImageId": "uimage-xxx",
  "RetCode": 0
}
```





