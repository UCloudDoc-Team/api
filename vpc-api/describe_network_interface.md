# 展示虚拟网卡信息 - DescribeNetworkInterface

## 简介

展示虚拟网卡信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkInterface)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkInterface`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | 所属VPC |No|
| **SubnetId** | string | 所属子网 |No|
| **InterfaceId.N** | string | 虚拟网卡ID,可指定 0\~n |No|
| **OnlyDefault** | boolean | 若为true 只返回默认网卡<br />默认为false |No|
| **NoRecycled** | boolean | 若为true 过滤绑定在回收站主机中的网卡。默认为false。 |No|
| **Tag** | string | 业务组 |No|
| **Limit** | int | 默认为20 |No|
| **Offset** | int | 默认为0 |No|
| **WithSecGroup** | boolean | 是否展示安全组信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NetworkInterfaceSet** | array[[*NetworkInterface*](#NetworkInterface)] | 虚拟网卡信息 |**Yes**|
| **TotalCount** | int | 虚拟网卡总数 |No|

#### 数据模型


#### NetworkInterface

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **InterfaceId** | string | 虚拟网卡资源ID |**Yes**|
| **VPCId** | string | 所属VPC |**Yes**|
| **SubnetId** | string | 所属子网 |**Yes**|
| **PrivateIpSet** | array[string] | 关联内网IP。当前一个网卡仅支持绑定一个内网IP |**Yes**|
| **MacAddress** | string | 关联Mac |**Yes**|
| **Status** | int | 绑定状态 |**Yes**|
| **EIPIdSet** | array[string] | EIP Id 集合 |**Yes**|
| **FirewallIdSet** | array[string] | 防火墙 ID 集合 |**Yes**|
| **FirewallSet** | array[[*FwInfo*](#FwInfo)] | 防火墙信息 |**Yes**|
| **EipDirectMode** | boolean | EIP 直通 false：不是，true：是 |**Yes**|
| **EipDirectionVersion** | int | EIP 直通版本信息 |**Yes**|
| **DefaultOutput** | string | 默认IP 出口 |**Yes**|
| **PrivateIp** | array[[*UNIIpInfo*](#UNIIpInfo)] | 私有 IP 信息 |**Yes**|
| **IPv6AddressInfo** | array[[*SimpleIPv6AddressInfo*](#SimpleIPv6AddressInfo)] | IPv6 地址信息 |**Yes**|
| **IPv6Gateway** | string | IPv6 网关地址 |**Yes**|
| **IPv6Mask** | int | IPv6 掩码 |**Yes**|
| **OperatorName** | string | 运营商 |**Yes**|
| **SecGroupCount** | int | 关联安全组数量 |No|
| **SecGroup** | array[[*SecGroup*](#SecGroup)] | 关联安全组信息 |No|
| **Name** | string | 虚拟网卡名称 |No|
| **Netmask** | string | 内网IP掩码 |No|
| **Gateway** | string | 默认网关 |No|
| **AttachInstanceId** | string | 绑定实例资源ID |No|
| **Default** | boolean | 是否是绑定实例的默认网卡 false:不是 true:是 |No|
| **CreateTime** | int | 创建时间 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 业务组 |No|
| **PrivateIpLimit** | array[[*UNIQuotaInfo*](#UNIQuotaInfo)] | 私有 IP 配额 |No|

#### FwInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 防火墙资源 ID |No|
| **Name** | string | 防火墙资源名称 |No|

#### UNIIpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IpType** | string | ip类型 SecondaryIp/PrimaryIp |No|
| **IpAddr** | array[string] | ip 地址 |No|

#### SimpleIPv6AddressInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPv6Address** | string | IPv6 地址 |No|
| **IPv6Id** | string | IPv6 资源 ID |No|
| **Attribute** | string | 属性 |No|

#### SecGroup

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 安全组名称 |**Yes**|
| **Priority** | int | 关联优先级 |No|
| **SecGroupId** | string | 安全组ID |No|

#### UNIQuotaInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PrivateIpCount** | int | 网卡拥有的内网IP数量 |No|
| **PrivateIpQuota** | int | 网卡内网IP配额 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNetworkInterface
&Region=cn-zj
&ProjectId=GrhtRoeW
&VPCId=HtyqlvnD
&SubnetId=wDKbVBgv
&InterfaceId.N=fbZBJYKm
&OnlyDefault=true
&NoRecycled=false
&Tag=BcNsnzvn
&Limit=2
&Offset=7
&WithSecGroup=false
```

### 响应示例
    
```json
{
  "Action": "DescribeNetworkInterfaceResponse",
  "NetworkInterfaceSet": [
    {
      "AttachInstanceId": "rFTCEEXO",
      "CreateTime": 8,
      "Default": true,
      "DefaultOutput": "oQMKeDQE",
      "EIPIdSet": [
        "zMWGORbd"
      ],
      "EipDirectMode": false,
      "EipDirectVersion": 8,
      "FirewallIdSet": [
        "BMJvHDEm"
      ],
      "Gateway": "RttOHGIn",
      "InterfaceId": "bMzghuAx",
      "MacAddress": "qrKwhPrL",
      "Name": "gUkbpVLA",
      "Netmask": "BsrBMQMK",
      "PrivateIp": [
        {
          "IpAddr": [
            "gBSMmpMF"
          ],
          "IpType": "NxUNNPRV"
        }
      ],
      "PrivateIpLimit": {},
      "PrivateIpSet": [
        "qQgevdxI"
      ],
      "Remark": "FFbgXcpU",
      "Status": 0,
      "SubnetId": "xcjnhLNT",
      "Tag": "FalYfERG",
      "VPCId": "kDweFhmN"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





