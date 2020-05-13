# 获取VPN网关信息 - DescribeVPNGateway

## 简介

获取VPN网关信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVPNGateway)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVPNGateway`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPNGatewayIds.N** | string | VPN网关的资源ID，例如VPNGatewayIds.0代表希望获取VPN网关1的信息，VPNGatewayIds.1代表VPN网关2，如果为空，则返回当前Region中所有VPN网关的信息 |No|
| **VPCId** | string | VPC的资源ID，返回指定的VPC下的所有VPN网关的信息。默认返回当前Region中所有VPN网关实例的信息 |No|
| **Offset** | int | 数据偏移量。默认为0 |No|
| **Tag** | string | 业务组名称，若指定则返回指定的业务组下的所有VPN网关的信息。 |No|
| **Limit** | int | 数据分页值。默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的VPN网关总数 |No|
| **DataSet** | array[[*VPNGatewayDataSet*](#VPNGatewayDataSet)] | 获取的VPN网关信息列表，每项参数详见 VPNGatewayDataSet |No|

#### 数据模型


#### VPNGatewayDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VPNGatewayId** | string | 网关Id |No|
| **VPNGatewayName** | string | 网关名字 |No|
| **Tag** | string | 网关业务组 |No|
| **Remark** | string | 网关备注 |No|
| **VPCId** | string | 所属VPCId |No|
| **VPCName** | string | 所属VPC名字 |No|
| **ChargeType** | string | 付费类型 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **AutoRenew** | string | 是否自动续费 |No|
| **Grade** | string | 网关类型 |No|
| **EIP** | string | 绑定EIP的IP地址 |No|
| **EIPType** | string | EIP类型 |No|
| **EIPId** | string | EIPID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeVPNGateway
&Region=cn-sh2
&ProjecId=org-XXXX
&VPNGatewayId.0=vpngw-XXXX
&VPNGatewayId.1=vpngw-XXXX
&VPCId=uvnet-XXXX
&Offset=2
&Limit=3
&Tag=Default
```

### 响应示例
    
```json
{
  "Action": "DescribeVPNGatewayResponse",
  "DataSet": [
    {
      "AutoRenew": "Yes",
      "ChargeType": "Month",
      "CreateTime": 1530070980,
      "EIP": "106.75.XX.78",
      "EIPId": "eip-XX",
      "EIPType": "Bgp",
      "ExpireTime": 1530374400,
      "Grade": "Standard",
      "Remark": "",
      "Tag": "Default",
      "VPCId": "uvnet-XX",
      "VPCName": "",
      "VPNGatewayId": "vpngw-XXX",
      "VPNGatewayName": "111111"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





