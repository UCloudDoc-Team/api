# 获取子网信息 - DescribeSubnet

## 简介

获取子网信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSubnet)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSubnet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SubnetIds.N** | string | 子网id数组，适用于一次查询多个子网信息 |No|
| **SubnetId** | string | 子网id，适用于一次查询一个子网信息 |No|
| **RouteTableId** | string | 路由表Id |No|
| **VPCId** | string | VPC资源id |No|
| **Tag** | string | 业务组名称，默认为Default |No|
| **Offset** | int | 偏移量，默认为0 |No|
| **Limit** | int | 列表长度，默认为20 |No|
| **ShowAvailableIPs** | boolean | 是否返回子网的可用IP数，true为是，false为否，默认不返回 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 子网总数量 |**Yes**|
| **DataSet** | array[[*SubnetInfo*](#SubnetInfo)] | 子网信息数组，具体资源见下方SubnetInfo |**Yes**|

#### 数据模型


#### SubnetInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区名称 |No|
| **IPv6Network** | string | 子网关联的IPv6网段 |No|
| **VPCId** | string | VPCId |No|
| **VPCName** | string | VPC名称 |No|
| **SubnetId** | string | 子网Id |No|
| **SubnetName** | string | 子网名称 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 业务组 |No|
| **SubnetType** | int | 子网类型 |No|
| **Subnet** | string | 子网网段 |No|
| **Netmask** | string | 子网掩码 |No|
| **Gateway** | string | 子网网关 |No|
| **CreateTime** | int | 创建时间 |No|
| **HasNATGW** | boolean | 是否有natgw |No|
| **RouteTableId** | string | 路由表Id |No|
| **AvailableIPs** | int | 可用IP数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSubnet
&ProjectId=org-XXXX
&Region=cn-sh2
&SubnetId=subnet-XXX
&VPCId=uvnet-XXXX
&Tag=tag
&Offset=0
&Limit=20
&RouteTableId=KbKrefnV
&ShowAvailableIPs=false
```

### 响应示例
    
```json
{
  "Action": "DescribeSubnetResponse",
  "DataSet": [
    {
      "CreateTime": 1528353483,
      "Gateway": "172.16.XX.1",
      "HasNATGW": false,
      "Name": "test-s1",
      "Netmask": "24",
      "Remark": "test",
      "RouteTableId": "routetable-XXXX",
      "Subnet": "172.16.XXX.0",
      "SubnetId": "subnet-XXXXX",
      "SubnetName": "test-s1",
      "SubnetType": 2,
      "Tag": "Default",
      "VPCId": "uvnet-XXXX",
      "VPCName": "test",
      "VRouterId": "Default_VRouter",
      "Zone": "cn-sh2-01"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





