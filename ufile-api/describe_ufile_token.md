# 获取令牌信息 - DescribeUFileToken

## 简介

获取令牌信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFileToken)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFileToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TokenId** | string | 令牌ID，只返回指定ID信息，否则拉取所有令牌 |No|
| **TokenName** | string | 令牌名称，只返回指定令牌名称信息，否则拉取所有令牌 |No|
| **Display** | int | 0表示显示部分token信息；不传递和其他情况表示显示全部token信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileTokenSet*](#UFileTokenSet)] | 令牌描述信息 |**Yes**|

#### 数据模型


#### UFileTokenSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TokenId** | string | 令牌ID |**Yes**|
| **TokenName** | string | 令牌名称 |**Yes**|
| **PublicKey** | string | 令牌公钥 |**Yes**|
| **PrivateKey** | string | 令牌私钥 |**Yes**|
| **AllowedOps** | array[string] | 令牌允许执行的操作，[ TOKEN_ALLOW_NONE , TOKEN_ALLOW_READ , TOKEN_ALLOW_WRITE , TOKEN_ALLOW_DELETE , TOKEN_ALLOW_LIST, TOKEN_ALLOW_IOP , TOKEN_ALLOW_DP ] |**Yes**|
| **AllowedPrefixes** | array[string] | 令牌允许操作的key前缀 |**Yes**|
| **AllowedBuckets** | array[string] | 令牌允许操作的bucket |**Yes**|
| **ExpireTime** | int | 令牌的超时时间点 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|
| **Region** | string | 所属地区 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFileToken
&ProjectId=org-xxx
&TokenId=679c7e5e-74b8-4048-b622-33dd4e8634de
&Region=cn-bj
&Display=2
&TokenName=BFCOSzvM
```

### 响应示例
    
```json
{
  "Action": "DescribeUFileTokenResponse",
  "DataSet": [
    {
      "AllowedBuckets": [
        "bucket1",
        "bucket2"
      ],
      "AllowedOps": [
        "TOKEN_ALLOW_READ",
        "TOKEN_ALLOW_WRITE"
      ],
      "AllowedPrefixes": [
        "test/test",
        "test1/test1"
      ],
      "ExpireTime": 4102416000,
      "PrivateKey": "7b01a354-adb2-49a1-9f68-af814e884c29",
      "PublicKey": "TOKEN_679c7e5e-74b8-4048-b622-33dd4e8634de",
      "TokenId": "679c7e5e-74b8-4048-b622-33dd4e8634de",
      "TolenName": "testname"
    },
    {
      "AllowedBuckets": [
        "bucket1",
        "bucket2"
      ],
      "AllowedOps": [
        "TOKEN_ALLOW_READ",
        "TOKEN_ALLOW_WRITE"
      ],
      "AllowedPrefixes": [
        "test/test",
        "test1/test1"
      ],
      "ExpireTime": 4102416000,
      "PrivateKey": "7b01a354-adb2-49a1-9f68-af814e884c27",
      "PublicKey": "TOKEN_679c7e5e-74b8-4048-b622-33dd4e8634dc",
      "TokenId": "679c7e5e-74b8-4048-b622-33dd4e8634dc",
      "TokenName": "test1name"
    }
  ],
  "RetCode": 0
}
```





