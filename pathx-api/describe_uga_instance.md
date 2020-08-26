# 获取全球加速服务加速配置信息 - DescribeUGAInstance

## 简介

获取全球加速服务加速配置信息，指定实例ID返回单个实例。未指定实例ID时 指定分页参数 则按创建时间降序 返回记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUGAInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGAInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UGAId** | string | 加速配置实例ID，如果传了实例ID 则返回匹配实例ID的记录；如果没传则返回 ProjectId 下全部实例且符合分页要求 |No|
| **Limit** | int | 返回的最大条数，默认为100，最大值400 |No|
| **Offset** | int | 偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGAList** | array[[*UGAAInfo*](#UGAAInfo)] | 全球加速实例信息列表 |No|
| **TotalCount** | int | 符合条件的总数 |No|

#### 数据模型


#### UGAAInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGAId** | string | 加速配置实例ID |**Yes**|
| **CName** | string | 加速域名，请在加速区域配置您的业务域名的CName记录值为加速域名 |**Yes**|
| **UGAName** | string | 加速配置名称 |**Yes**|
| **IPList** | array[string] | 源站IP列表，多个值由半角英文逗号相隔 |No|
| **Domain** | string | 源站域名 |No|
| **Location** | string | 源站所在区域，加速实例在绑定线路后会自动设置该值。console页面上通过该值过滤加速实例可以绑定的upath实例。注意：缺少该值会导致在console上无法修改线路 |No|
| **UPathSet** | array[[*UPathSet*](#UPathSet)] | 绑定的加速线路 |No|
| **TaskSet** | array[[*UGAATask*](#UGAATask)] | 端口配置信息（不再维护，建议使用ForwarderSet） |No|
| **L4ForwarderSet** | array[[*UGAL4Forwarder*](#UGAL4Forwarder)] | UGA 4层转发器配置，记录接入或回源端口，接入或回源协议信息 |No|
| **L7ForwarderSet** | array[[*UGAL7Forwarder*](#UGAL7Forwarder)] | UGA 7层转发器配置，记录接入或回源端口，接入或回源协议信息 如绑定证书会返回证书ID |No|
| **OutPublicIpList** | array[[*OutPublicIpInfo*](#OutPublicIpInfo)] | 线路出口IP地址 |No|

#### UPathSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPathName** | string | UPath名字 |No|
| **UPathId** | string | UPath 实例ID |No|
| **Bandwidth** | int | 带宽 Mbps, 1\~800Mbps |No|
| **LineId** | string | 线路ID |No|
| **LineFromName** | string | 线路起点中文名字，加速区域 |No|
| **LineToName** | string | 线路对端中文名字，源站区域 |No|
| **LineFrom** | string | 线路起点英文代号，加速区域 |No|
| **LineTo** | string | 线路对端英文代号，源站区域 |No|

#### UGAATask

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Port** | int | 接入端口 |**Yes**|
| **Protocol** | string | 转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发 |**Yes**|

#### UGAL4Forwarder

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Port** | int | 接入端口 |**Yes**|
| **Protocol** | string | 转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发 |**Yes**|
| **RSPort** | int | RSPort，源站监听端口 |**Yes**|

#### UGAL7Forwarder

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Port** | int | 接入端口 |**Yes**|
| **Protocol** | string | 转发协议，枚举值["TCP"，"UDP"，"HTTPHTTP"，"HTTPSHTTP"，"HTTPSHTTPS"]。TCP和UDP代表四层转发，其余为七层转发 |**Yes**|
| **RSPort** | int | RSPort，源站监听端口 |**Yes**|
| **SSLId** | string | 证书ID |No|
| **SSLName** | string | 证书名称 |No|

#### OutPublicIpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string |  线路出口EIP |No|
| **Area** | string | 线路出口机房代号 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGAInstance
&ProjectId=org-xxxx
&UGAId=uga-5ygl0d
&Limit=10
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "DescribeUGAInstanceResponse",
  "Message": "",
  "RetCode": 0,
  "TotalCount": 1,
  "UGAList": [
    {
      "CName": "xbc287.pathx.ucloudgda.com",
      "Domain": "github.com",
      "IPList": [
        ""
      ],
      "L4ForwarderSet": [
        {
          "Port": 443,
          "Protocol": "TCP",
          "RSPort": 443
        }
      ],
      "L7ForwarderSet": [],
      "Location": "北美",
      "OutPublicIpList": [
        {
          "Area": "us-ca",
          "IP": "107.150.101.244"
        },
        {
          "Area": "us-ca",
          "IP": "107.150.102.54"
        },
        {
          "Area": "us-ca",
          "IP": "107.150.102.58"
        },
        {
          "Area": "us-ca",
          "IP": "107.150.102.63"
        },
        {
          "Area": "us-ca",
          "IP": "107.150.102.68"
        },
        {
          "Area": "us-ca",
          "IP": "107.150.102.88"
        }
      ],
      "TaskSet": [
        {
          "Port": 443,
          "Protocol": "TCP",
          "RSPort": 0
        }
      ],
      "UGAId": "uga-5ygl0d",
      "UGAName": "github加速",
      "UPathSet": [
        {
          "Bandwidth": 1,
          "LineFrom": "cn-gd",
          "LineFromName": "中国(多地)",
          "LineId": "line_cn-us-ca",
          "LineTo": "us-ca",
          "LineToName": "洛杉矶",
          "UPathId": "upath-xcacoz",
          "UPathName": "中美加速"
        }
      ]
    }
  ]
}
```





