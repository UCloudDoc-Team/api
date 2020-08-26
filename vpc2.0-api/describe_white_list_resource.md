# 展示NAT网关白名单资源列表 - DescribeWhiteListResource

## 简介

展示NAT网关白名单资源列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeWhiteListResource)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWhiteListResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目id |**Yes**|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **NATGWIds.N** | string | NAT网关的Id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*NatGWWhitelistDataSet*](#NatGWWhitelistDataSet)] | 白名单资源的详细信息，详见DescribeResourceWhiteListDataSet |**Yes**|
| **TotalCount** | int | 上述DataSet总数量 |**Yes**|

#### 数据模型


#### NatGWWhitelistDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NATGWId** | string | NATGateWay Id |**Yes**|
| **IfOpen** | int | 白名单开关标记 |**Yes**|
| **ObjectIPInfo** | array[[*DescribeWhiteListResourceObjectIPInfo*](#DescribeWhiteListResourceObjectIPInfo)] | 白名单详情 |**Yes**|

#### DescribeWhiteListResourceObjectIPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GwType** | string | natgw字符串 |**Yes**|
| **PrivateIP** | string | 白名单资源的内网IP |**Yes**|
| **ResourceId** | string | 白名单资源Id信息 |**Yes**|
| **ResourceName** | string | 白名单资源名称 |**Yes**|
| **ResourceType** | string | 白名单资源类型 |**Yes**|
| **SubResourceId** | string | 资源绑定的虚拟网卡的实例ID |**Yes**|
| **SubResourceName** | string | 资源绑定的虚拟网卡的实例名称 |**Yes**|
| **SubResourceType** | string | 资源绑定的虚拟网卡的类型 |**Yes**|
| **VPCId** | string | 白名单资源所属VPCId |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWhiteListResource
&Region=cn-bj2
&NATGWIds.0=NbbRAeIJ
&ProjectId=KwzficzX
```

### 响应示例
    
```json
{
  "Action": "DescribeWhiteListResourceResponse",
  "DataSet": [
    "nSRkanNq",
    "TkHTtQoc",
    "ONBPkxrr",
    "aoGskHfU",
    "suKalXHG",
    "UQMozDcj",
    "JVOeFxGX",
    "EUbVfeda"
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





