# 创建虚拟网卡 - CreateNetworkInterface

## 简介

创建虚拟网卡






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateNetworkInterface)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNetworkInterface`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | 所属VPCID |**Yes**|
| **SubnetId** | string | 所属子网ID |**Yes**|
| **Name** | string | 虚拟网卡名称，默认为 NetworkInterface |No|
| **PrivateIp.N** | string | 指定内网IP。当前一个网卡仅支持绑定一个内网IP |No|
| **SecurityGroupId** | string | 防火墙GroupId，默认：Web推荐防火墙 <br />可由DescribeSecurityGroupResponse中的GroupId取得 |No|
| **Tag** | string | 业务组 |No|
| **Remark** | string | 备注 |No|
| **SecurityMode** | int | 指定使用 安全组还是防火墙。为 0 时绑定防火墙，为1时绑定安全组 |No|
| **PrioritySecGroup.N.Priority** | int | 安全组优先级 |No|
| **PrioritySecGroup.N.SecGroupId** | string | 安全组 ID |No|
| **EipDirectMode** | boolean | 是否开启EIP直通，默认false |No|
| **EipDirectVersion** | int | 枚举值<br />1:EIP网卡可见<br />2:EIP直通<br />默认为1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NetworkInterface** | [*NetworkInterfaceInfo*](#NetworkInterfaceInfo) | 若创建成功，则返回虚拟网卡信息。创建失败，无此参数 |No|

#### 数据模型


#### NetworkInterfaceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **InterfaceId** | string | 虚拟网卡资源ID |**Yes**|
| **VPCId** | string | 所属VPC |**Yes**|
| **SubnetId** | string | 所属子网 |**Yes**|
| **PrivateIpSet** | array[string] | 关联内网IP。当前一个网卡仅支持绑定一个内网IP |**Yes**|
| **MacAddress** | string | 关联Mac |**Yes**|
| **Status** | int | 绑定状态 |**Yes**|
| **Name** | string | 虚拟网卡名称 |No|
| **Netmask** | string | 内网IP掩码 |No|
| **Gateway** | string | 默认网关 |No|
| **AttachInstanceId** | string | 绑定实例资源ID |No|
| **Default** | boolean | 是否是绑定实例的默认网卡 false:不是 true:是 |No|
| **CreateTime** | int | 创建时间 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 业务组 |No|
| **EipDirectMode** | boolean | 是否开启EIP直通模式 |No|
| **EipDirectVersion** | int | EIP直通版本 |No|

## 示例

### 请求示例
    
```
{
	"Action": "CreateNetworkInterface",
        "Region": "cn-bj2",
	"ProjectId": "org-test",
	"VPCId": "uvnet-331hnn",
	"SubnetId": "subnet-hlfs4x",
	"Name": "helloucloud",
	"Tag": "test",
	"Remark": "test",
	"PrivateIp.0": "10.21.11.11",
	"SecurityGroupId": "0"
}
&SecurityMode=2
&PrioritySecGroup.N=UassEvha
&EipDirectMode=false
&PrioritySecGroup.N.SecGroupId=VoMaPJyE
&EipDirectVersion=6
```

### 响应示例
    
```json
{
  "Action": "CreateNetworkInterfaceResponse",
  "NetworkInterface": {
    "AttachInstanceId": "",
    "CreateTime": 1513745006,
    "Default": false,
    "Gateway": "10.99.2.1",
    "InterfaceId": "uni-wbybfs",
    "MacAddress": "52:54:00:1F:A7:F7",
    "Name": "helloucloud",
    "Netmask": "255.255.255.0",
    "PrivateIpSet": [
      "10.99.2.81"
    ],
    "Remark": "test",
    "Status": 0,
    "SubnetId": "subnet-hlfs4x",
    "Tag": "test",
    "VPCId": "uvnet-331hnn"
  },
  "RetCode": 0
}
```





