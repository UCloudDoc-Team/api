# 展示云主机绑定的网卡信息 - DescribeInstanceNetworkInterface

## 简介

展示云主机绑定的网卡信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeInstanceNetworkInterface)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeInstanceNetworkInterface`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 云主机ID |**Yes**|
| **Offset** | int | 默认为0 |No|
| **Limit** | int | 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NetworkInterfaceSet** | array[[*NetworkInterface*](#NetworkInterface)] | 虚拟网卡信息 |**Yes**|

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
| **PrivateIp** | array[string] | 网卡的内网IP信息 |**Yes**|
| **Name** | string | 虚拟网卡名称 |No|
| **Netmask** | string | 内网IP掩码 |No|
| **Gateway** | string | 默认网关 |No|
| **AttachInstanceId** | string | 绑定实例资源ID |No|
| **Default** | boolean | 是否是绑定实例的默认网卡 false:不是 true:是 |No|
| **CreateTime** | int | 创建时间 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 业务组 |No|
| **EIPIdSet** | array[string] | 虚拟网卡绑定的EIP ID信息 |No|
| **FirewallIdSet** | array[string] | 虚拟网卡绑定的防火墙ID信息 |No|
| **PrivateIplimit** | array[string] | 网卡的内网IP配额信息 |No|

## 示例

### 请求示例
    
```
{
	"Action": "DescribeInstanceNetworkInterface",
	"Region": "pre",
	"InstanceId": "uhost-p5ye1u"
}
```

### 响应示例
    
```json
{
  "Action": "DescribeInstanceNetworkInterfaceResponse",
  "NetworkInterfaceSet": [
    {
      "AttachInstanceId": "uhost-p5ye1u",
      "CreateTime": 1513238069,
      "Default": true,
      "Gateway": "10.21.0.1",
      "InterfaceId": "uni-xe1xkj",
      "MacAddress": "52:54:00:7D:24:FF",
      "Name": "chd-2",
      "Netmask": "255.255.0.0",
      "PrivateIpSet": [
        "10.21.180.210"
      ],
      "Remark": "chd",
      "Status": 1,
      "SubnetId": "subnet-pnctmk",
      "Tag": "chd_group",
      "VPCId": "uvnet-lksdw0"
    }
  ],
  "RetCode": 0
}
```





