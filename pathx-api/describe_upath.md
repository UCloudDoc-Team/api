# 获取加速线路信息 - DescribeUPath

## 简介

获取加速线路信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUPath)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPath`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UPathId** | string | 如果不填参数 返回 ProjectId 下所有的线路资源，填此参数则返回upath实例ID匹配的线路 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UPathSet** | array[[*UPathInfo*](#UPathInfo)] | 线路信息数组 |**Yes**|

#### 数据模型


#### UPathInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PostPaid** | boolean | 是否为后付费实例 |No|
| **ChargeType** | string | 计费模式，默认为Month 按月收费,可选范围['Month','Year','Dynamic'] |No|
| **Name** | string | UPath实例名字 |No|
| **UPathId** | string | UPath加速线路实例ID |No|
| **Bandwidth** | int | 带宽，单位Mbps |No|
| **LineId** | string | 选择的线路 |No|
| **UGAList** | array[[*PathXUGAInfo*](#PathXUGAInfo)] | 与该UPath绑定的UGA列表 |No|
| **CreateTime** | int | UPath创建的时间，10位时间戳 |No|
| **ExpireTime** | int | UPath的过期时间，10位时间戳 |No|
| **LineFromName** | string | 线路入口名称 |No|
| **LineToName** | string | 线路出口名称 |No|
| **OutPublicIpList** | array[[*OutPublicIpInfo*](#OutPublicIpInfo)] | 线路出口IP数组 |No|

#### PathXUGAInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGAId** | string | 加速配置ID |No|
| **IPList** | array[string] | 源站IP列表，多个值由半角英文逗号相隔 |No|
| **Domain** | string | 源站域名 |No|

#### OutPublicIpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string |  线路出口EIP |No|
| **Area** | string | 线路出口机房代号 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPath
&ProjectId=org-xxxx
&UPathId=upath-2noe2u
```

### 响应示例
    
```json
{
  "Action": "DescribeUPathResponse",
  "Message": "",
  "RetCode": 0,
  "UPathSet": [
    {
      "Bandwidth": 1,
      "ChargeType": "Month",
      "CreateTime": 1542029575,
      "ExpireTime": 1569859200,
      "LineFromName": "中国(多地)",
      "LineId": "line_cn_afr-nigeria",
      "LineToName": "拉各斯",
      "Name": "中国多地到拉各斯_0",
      "OutPublicIpList": [
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.87"
        },
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.102"
        },
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.64"
        },
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.105"
        },
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.15"
        },
        {
          "Area": "afr-nigeria",
          "IP": "152.32.140.55"
        }
      ],
      "PostPaid": false,
      "UGAList": [
        {
          "Domain": "",
          "IPList": [
            "152.32.140.170"
          ],
          "UGAId": "uga-2yftnppa"
        }
      ],
      "UPathId": "upath-2noe2u"
    }
  ]
}
```





