# 获取主机业务组列表 - DescribeUHostTags

## 简介

获取指定数据中心的业务组列表。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUHostTags)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUHostTags`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 已有主机的业务组总数 |No|
| **TagSet** | array[[*UHostTagSet*](#UHostTagSet)] | 业务组集合见 UHostTagSet |No|

#### 数据模型


#### UHostTagSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Tag** | string | 业务组名称 |No|
| **TotalCount** | int | 该业务组中包含的主机个数 |No|
| **Zone** | string | 可用区 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUHostTags
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeUHostTagsResponse",
  "RetCode": 0,
  "TagSet": [
    {
      "Tag": "Default",
      "TotalCount": 2,
      "Zone": "xxx"
    }
  ],
  "TotalCount": 1
}
```





