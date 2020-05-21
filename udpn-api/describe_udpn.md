# 描述 UDPN - DescribeUDPN

## 简介

描述 UDPN






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDPN)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDPN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **UDPNId** | string | 申请到的 UDPN 资源 ID。若为空，则查询该用户在机房所有的专线信息。非默认项目资源，需填写ProjectId |No|
| **Offset** | int | 列表起始位置偏移量，默认为 0 |No|
| **Limit** | int | 返回数据长度，默认为 20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 查询到的总数量 |**Yes**|
| **DataSet** | array[[*UDPNData*](#UDPNData)] | UDPN详情 |No|

#### 数据模型


#### UDPNData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UDPNId** | string | UDPN 资源短 ID |**Yes**|
| **Peer1** | string | 可用区域 1 |**Yes**|
| **Peer2** | string | 可用区域 2 |**Yes**|
| **ChargeType** | string | 计费类型 |**Yes**|
| **Bandwidth** | string | 带宽 |**Yes**|
| **CreateTime** | int | unix 时间戳 创建时间 |**Yes**|
| **ExpireTime** | int | unix 时间戳 到期时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDPN
&UDPNId=udpn-uy3qvu
&ProjectId＝test
```

### 响应示例
    
```json
{
  "Action": "DescribeUDPNResponse",
  "DataSet": [
    {
      "Bandwidth": 2,
      "ChargeType": "Month",
      "CreateTime": 1508413095,
      "ExpireTime": 1509465600,
      "Peer1": "cn-bj2",
      "Peer2": "cn-gd",
      "UDPNId": "udpn-uy3qvu"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





