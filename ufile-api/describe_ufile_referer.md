# 对象存储防盗链列表 - DescribeUFileReferer

## 简介

对象存储防盗链列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFileReferer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFileReferer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BucketName** | string | 存储空间名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RefererType** | int | 防盗链Referer类型，支持两种类型，1黑名单，2白名单；未开启referer时不返回此参数 |**Yes**|
| **RefererList** | array[string] | 防盗链Referer规则列表；未开启referer时不返回此参数 |**Yes**|
| **NullRefer** | boolean | ReferType为白名单时，NullRefer为false代表不允许NULL refer访问，为true代表允许Null refer访问; 未开启referer时不返回此参数 |**Yes**|
| **RefererStatus** | string | 防盗链功能是否开启，"on"表示开启，"off"表示关闭 |No|
| **BlackList** | array[string] | 黑名单列表 |No|
| **WhiteList** | array[string] | 白名单列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFileReferer
&Region=cn-zj
&ProjectId=ywgucrMT
&BucketName=fwEbslNB
```

### 响应示例
    
```json
{
  "Action": "DescribeUFileRefererResponse",
  "BlackList": [
    "KhHaLirZ"
  ],
  "NullRefer": false,
  "RefererList": [
    "KkbcNVJF"
  ],
  "RefererStatus": "gIBfLaIP",
  "RefererType": 8,
  "RetCode": 0,
  "WhiteList": [
    "xKxbdXUL"
  ]
}
```





