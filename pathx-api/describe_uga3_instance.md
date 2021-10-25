# 获取全球统一接入加速服务加速配置信息 - DescribeUGA3Instance

## 简介

获取全球统一接入加速服务加速配置信息，指定实例ID返回单个实例。未指定实例ID时 指定分页参数 则按创建时间降序 返回记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUGA3Instance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGA3Instance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 加速配置实例ID，如果传了实例ID 则返回匹配实例ID的记录；如果没传则返回 ProjectId 下全部实例且符合分页要求 |No|
| **Limit** | int | 返回的最大条数，默认为100，最大值400 |No|
| **Offset** | int | 偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ForwardInstanceInfos** | array[[*ForwardInfo*](#ForwardInfo)] | 全球加速实例信息列表 |No|
| **TotalCount** | int | 符合条件的总数 |No|

#### 数据模型


#### ForwardInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **InstanceId** | string | 加速配置ID |**Yes**|
| **CName** | string | 加速域名 |**Yes**|
| **Name** | string | 加速实例名称 |**Yes**|
| **AccelerationArea** | string | 加速大区代码 |**Yes**|
| **AccelerationAreaName** | string | 加速大区名称 |**Yes**|
| **AccelerationAreaInfos** | array[[*AccelerationAreaInfos*](#AccelerationAreaInfos)] | 加速节点列表 |**Yes**|
| **EgressIpList** | array[[*OutPublicIpInfo*](#OutPublicIpInfo)] | 回源出口IP地址 |**Yes**|
| **Bandwidth** | int | 购买的带宽值 |**Yes**|
| **OriginArea** | string | 源站中文名 |**Yes**|
| **OriginAreaCode** | string | 源站AreaCode |**Yes**|
| **CreateTime** | int | 资源创建时间 |**Yes**|
| **ExpireTime** | int | 资源过期时间 |**Yes**|
| **ChargeType** | string | 计费方式 |**Yes**|
| **Remark** | string | 备注 |No|
| **PortSets** | array[[*ForwardTask*](#ForwardTask)] | 端口列表 |No|
| **IPList** | array[string] | 源站IP列表，多个值由半角英文逗号相隔 |No|
| **Domain** | string | 源站域名 |No|

#### AccelerationAreaInfos

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccelerationArea** | string | 加速区code |**Yes**|
| **AccelerationNodes** | array[[*SrcAreaInfo*](#SrcAreaInfo)] | 加速节点信息 |**Yes**|

#### OutPublicIpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string |  线路回源节点EIP |No|
| **Area** | string | 线路回源节点机房代号 |No|

#### ForwardTask

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Protocol** | string | 转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"，"WSWS"，"WSSWS"，"WSSWSS"]。TCP和UDP代表四层转发，其余为七层转发。 |**Yes**|
| **RSPort** | int | 源站服务器监听的端口号 |**Yes**|
| **Port** | int | 加速端口 |**Yes**|

#### SrcAreaInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaCode** | string | AreaCode ,城市机场代码 |**Yes**|
| **Area** | string | AreaCode对应城市名 |**Yes**|
| **FlagEmoji** | string | 国旗Emoji |**Yes**|
| **FlagUnicode** | string | 国旗Unicode |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGA3Instance
&ProjectId=ScivyJPS
&InstanceId=aFTuTiWN
&Limit=7
&Offset=7
```

### 响应示例
    
```json
{
  "Action": "DescribeUGA3InstanceResponse",
  "ForwardInstanceInfos": [
    {
      "Bandwidth": 6,
      "CName": "tXVQgqPE",
      "Domain": "UCiojbNT",
      "IPList": [
        "jJvXIBHk"
      ],
      "InstanceId": "HAUdFuBI",
      "Name": "bZerLBBH",
      "OutpublicIpList": [
        "BgEcBTTy"
      ],
      "TaskSet": [
        {
          "Port": 0,
          "Protocol": "yes",
          "RSPort": 5
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 7
}
```





