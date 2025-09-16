# 获取NAT网关信息 - DescribeNATGW

## 简介

获取NAT网关信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNATGW)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNATGW`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NATGWIds.N** | string | NAT网关Id。默认为该项目下所有NAT网关 |No|
| **Offset** | int | 数据偏移量。默认为0 |No|
| **Limit** | int | 数据分页值。默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的实例的总数 |**Yes**|
| **DataSet** | array[[*NatGatewayDataSet*](#NatGatewayDataSet)] | 查到的NATGW信息列表 |No|

#### 数据模型


#### NatGatewayDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NATGWId** | string | natgw id |**Yes**|
| **NATGWName** | string | natgw名称 |**Yes**|
| **Tag** | string | 业务组 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **CreateTime** | int | natgw创建时间 |**Yes**|
| **FirewallId** | string | 绑定的防火墙Id |**Yes**|
| **VPCId** | string | 所属VPC Id |**Yes**|
| **SubnetSet** | array[[*NatGatewaySubnetSet*](#NatGatewaySubnetSet)] | 子网 Id |**Yes**|
| **IPSet** | array[[*NatGatewayIPSet*](#NatGatewayIPSet)] | 绑定的EIP 信息 |**Yes**|
| **VPCName** | string | VPC名称 |**Yes**|
| **IsSnatpoolEnabled** | string | 枚举值，“enable”，默认出口规则使用了负载均衡；“disable”，默认出口规则未使用负载均衡。 |**Yes**|
| **PolicyId** | array[string] | 转发策略Id |**Yes**|

#### NatGatewaySubnetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Subnet** | string | 子网网段 |**Yes**|
| **SubnetworkId** | string | 子网id |No|
| **SubnetName** | string | 子网名字 |No|

#### NatGatewayIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIPId** | string | 外网IP的 EIPId |**Yes**|
| **Weight** | int | 权重为100的为出口 |**Yes**|
| **BandwidthType** | string | EIP带宽类型 |**Yes**|
| **Bandwidth** | int | 带宽 |**Yes**|
| **IPResInfo** | array[[*NatGWIPResInfo*](#NatGWIPResInfo)] | 外网IP信息 |**Yes**|

#### NatGWIPResInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | IP的运营商信息 |**Yes**|
| **EIP** | string | 外网IP |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNATGW
&Region=xxx
&ProjectId=xxx
&NATGWIds.0=urIvqFth
&Offset=2
&Limit=8
```

### 响应示例
    
```json
{
  "Action": "DescribeNATGWResponse",
  "DataSet": [
    {
      "CreateTime": 1541056378,
      "FirewallId": "firewall-fadbay",
      "IPSet": [
        {
          "Bandwidth": 1,
          "BandwidthType": "Bandwidth",
          "EIPId": "eip-kti5zt",
          "EIPUUID": "eip-kti5zt",
          "IPResInfo": [
            {
              "EIP": "106.75.171.117",
              "OperatorName": "Bgp"
            }
          ],
          "Weight": 50
        }
      ],
      "NATGWId": "natgw-ay4tpe",
      "NATGWName": "nat-spider-test",
      "PolicyId": [],
      "Remark": "",
      "SubnetSet": [
        {
          "Subnet": "192.168.0.0/26",
          "SubnetName": "subnet-spider-test",
          "SubnetworkId": "subnet-kfi5wu",
          "SubnetworkUUID": "subnet-kfi5wu"
        }
      ],
      "Tag": "Default",
      "VPCId": "uvnet-4au5pv",
      "VPCName": "vpc-spider-test"
    },
    {
      "CreateTime": 1508817896,
      "FirewallId": "firewall-fadbay",
      "IPSet": [
        {
          "Bandwidth": 2,
          "BandwidthType": "Bandwidth",
          "EIPId": "eip-zqnjjh",
          "EIPUUID": "eip-zqnjjh",
          "IPResInfo": [
            {
              "EIP": "106.75.154.101",
              "OperatorName": "Bgp"
            }
          ],
          "Weight": 50
        }
      ],
      "NATGWId": "natgw-d0ubto",
      "NATGWName": "xxxxxx",
      "PolicyId": [],
      "Remark": "",
      "SubnetSet": [
        {
          "Subnet": "10.14.128.0/17",
          "SubnetName": "subnet-quyang",
          "SubnetworkId": "subnet-t1lhkw",
          "SubnetworkUUID": "subnet-t1lhkw"
        }
      ],
      "Tag": "xxxx",
      "VPCId": "uvnet-cvkbyg",
      "VPCName": "DefaultVPC"
    },
    {
      "CreateTime": 1542097658,
      "FirewallId": "firewall-itqvoh",
      "IPSet": [
        {
          "Bandwidth": 1,
          "BandwidthType": "Bandwidth",
          "EIPId": "eip-1ir5ot",
          "EIPUUID": "eip-1ir5ot",
          "IPResInfo": [
            {
              "EIP": "106.75.188.86",
              "OperatorName": "Bgp"
            }
          ],
          "Weight": 50
        }
      ],
      "NATGWId": "natgw-frwr22",
      "NATGWName": "natgw容灾测试",
      "PolicyId": [],
      "Remark": "",
      "SubnetSet": [
        {
          "Subnet": "192.168.128.0/17",
          "SubnetName": "容灾测试11",
          "SubnetworkId": "subnet-jrqoqo",
          "SubnetworkUUID": "subnet-jrqoqo"
        }
      ],
      "Tag": "Default",
      "VPCId": "uvnet-2b15h0",
      "VPCName": "容灾测试11"
    },
    {
      "CreateTime": 1541043690,
      "FirewallId": "firewall-fadbay",
      "IPSet": [
        {
          "Bandwidth": 2,
          "BandwidthType": "Bandwidth",
          "EIPId": "eip-z1pnbo",
          "EIPUUID": "eip-z1pnbo",
          "IPResInfo": [
            {
              "EIP": "106.75.169.103",
              "OperatorName": "Bgp"
            }
          ],
          "Weight": 50
        }
      ],
      "NATGWId": "natgw-m1zj4z",
      "NATGWName": "abtesst_uxr_natgw_128",
      "PolicyId": [],
      "Remark": "",
      "SubnetSet": [
        {
          "Subnet": "10.128.10.0/24",
          "SubnetName": "abtest_uxr_subnet_128_1",
          "SubnetworkId": "subnet-ehkpnt",
          "SubnetworkUUID": "subnet-ehkpnt"
        },
        {
          "Subnet": "10.128.20.0/24",
          "SubnetName": "abtest_uxr_subnet_128_2",
          "SubnetworkId": "subnet-gttjg5",
          "SubnetworkUUID": "subnet-gttjg5"
        }
      ],
      "Tag": "Default",
      "VPCId": "uvnet-wmrnvj",
      "VPCName": "abtest_for_uxr"
    },
    {
      "CreateTime": 1541043825,
      "FirewallId": "firewall-fadbay",
      "IPSet": [
        {
          "Bandwidth": 2,
          "BandwidthType": "Bandwidth",
          "EIPId": "eip-nzkt14",
          "EIPUUID": "eip-nzkt14",
          "IPResInfo": [
            {
              "EIP": "106.75.138.165",
              "OperatorName": "Bgp"
            }
          ],
          "Weight": 50
        }
      ],
      "NATGWId": "natgw-0byxyr",
      "NATGWName": "abtest_uxr_natgw_129",
      "PolicyId": [],
      "Remark": "",
      "SubnetSet": [
        {
          "Subnet": "10.129.10.0/24",
          "SubnetName": "abtest_uxr_subnet_129",
          "SubnetworkId": "subnet-c4vxvi",
          "SubnetworkUUID": "subnet-c4vxvi"
        }
      ],
      "Tag": "Default",
      "VPCId": "uvnet-ebh53o",
      "VPCName": "abtest_for_uxr_2"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





