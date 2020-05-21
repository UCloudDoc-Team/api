# 获取客户VPN网关信息 - DescribeRemoteVPNGateway

## 简介

获取客户VPN网关信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeRemoteVPNGateway)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeRemoteVPNGateway`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **RemoteVPNGatewayIds.N** | string | 客户VPN网关的资源ID，例如RemoteVPNGatewayIds.0代表希望获取客户VPN网关1的信息，RemoteVPNGatewayIds.1代表客户VPN网关2，如果为空，则返回当前Region中所有客户VPN网关实例的信息 |No|
| **Tag** | string | 业务组名称，若指定则返回业务组下所有客户VPN网关信息 |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 数据分页值, 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 符合条件的客户VPN网关总数 |No|
| **DataSet** | array[[*RemoteVPNGatewayDataSet*](#RemoteVPNGatewayDataSet)] | 客户VPN网关列表, 每项参数详见 RemoteVPNGatewayDataSet |No|

#### 数据模型


#### RemoteVPNGatewayDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RemoteVPNGatewayId** | string | 客户网关ID |No|
| **RemoteVPNGatewayName** | string | 客户网关名称 |No|
| **RemoteVPNGatewayAddr** | string | 客户网关IP地址 |No|
| **Tag** | string | 用户组 |No|
| **Remark** | string | 备注 |No|
| **CreateTime** | int | 创建时间 |No|
| **ActiveTunnels** | string | 活跃的隧道id |No|
| **TunnelCount** | int | 活跃的隧道数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeRemoteVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&RemoteVPNGatewayId= remotevpngw-XXXXX
&Tag=Default
&Offset=1
&Limit=7
```

### 响应示例
    
```json
{
  "Action": "DescribeRemoteVPNGatewayResponse",
  "DataSet": [
    {
      "ActiveTunnels": [
        "vpntunnel-XXXX"
      ],
      "CreateTime": 1530070801,
      "Remark": "test",
      "RemoteVPNGatewayAddr": "1.1.XX.1",
      "RemoteVPNGatewayId": "remotevpngw-XXX",
      "RemoteVPNGatewayName": "test",
      "Tag": "Default",
      "TunnelCount": 1
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





