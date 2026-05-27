# 查询CE网关 - DescribeCEGateway

## 简介

查询CE网关，优先级 Region > PopGwId > VPNId






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCEGateway)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCEGateway`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PopGwId** | string | UWAN 实例 ID |No|
| **VPNId** | string | CE 实例 ID |No|
| **Offset** | int | 偏移量 |No|
| **Limit** | int | 限制量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |**Yes**|
| **VPNInfos** | array[[*VPNInfo*](#VPNInfo)] | CE信息 |**Yes**|

#### 数据模型


#### VPNInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **PopGwId** | string | UWAN 实例 ID |No|
| **PopGwName** | string | UWAN 资源名称 |No|
| **VPNId** | string | CE 网关 ID |No|
| **VPNTunnelIds** | array[string] | 子隧道 ID |No|
| **Name** | string | CE 名称 |No|
| **PublicIp** | string | 客户自有外网 IP |No|
| **IpType** | string | CE网关的接入方式：静态IP（Static）,动态IP（Dynamic） |No|
| **Status** | string | 状态（默认为空） |No|
| **CreateTime** | int | 创建时间 |No|
| **Remark** | string | CE备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCEGateway
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=IXjWhkkg
&PopGwId=RwJspbJH
&VPNId=VhPpqisY
&Offset=3
&Limit=7
```

### 响应示例
    
```json
{
  "Action": "DescribeCEGatewayResponse",
  "Message": "EtodBzlE",
  "RetCode": 0,
  "TotalCount": 8,
  "VPNInfos": [
    {
      "CreateTime": 2,
      "Name": "TDFThrRA",
      "PopGwId": "HDGvLNkt",
      "PopGwName": "GYwGhZOF",
      "PublicIp": "CrWcFYyN",
      "Status": "FLqpbDGL",
      "VPNId": "whqWVOhL",
      "VPNTunnelIds": [
        "Lnyqhuem"
      ]
    }
  ]
}
```





