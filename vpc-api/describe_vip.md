# 获取内网虚拟IP信息 - DescribeVIP

## 简介

获取内网VIP详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | vpc的id,指定SubnetId时必填 |No|
| **SubnetId** | string | 子网id，不指定则获取VPCId下的所有vip |No|
| **VIPId** | string | VIP ID |No|
| **Tag** | string | 业务组名称, 默认为 Default |No|
| **BusinessId** | string | 业务组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VIPSet** | array[[*VIPDetailSet*](#VIPDetailSet)] | 内网VIP详情，请见VIPDetailSet |No|
| **DataSet** | array[string] | 内网VIP地址列表 |No|
| **TotalCount** | int | vip数量 |No|

#### 数据模型


#### VIPDetailSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 地域 |No|
| **VIPId** | string | 虚拟ip id |No|
| **CreateTime** | int | 创建时间 |No|
| **RealIp** | string | 真实主机ip |No|
| **VIP** | string | 虚拟ip |No|
| **SubnetId** | string | 子网id |No|
| **VPCId** | string | VPC id |No|
| **Name** | string | VIP名称 |No|
| **Remark** | string | VIP备注 |No|
| **Tag** | string | VIP所属业务组 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeVIP
&Region=cn-bj2
&ProjectId=org-xxx
&Zone=cn-bj2-04
&VPCId=vnet-xxx
&VIPId=BPYTaGSD
&VIPId=ANzHspQH
```

### 响应示例
    
```json
{
  "Action": "DescribeVIPResponse",
  "DataSet": [
    "10.25.XX.XX"
  ],
  "RetCode": 0,
  "TotalCount": 1,
  "VIPSet": [
    {
      "CreateTime": 1521970238,
      "Name": "VIP",
      "RealIp": "",
      "Remark": "Default",
      "SubnetId": "subnet-XXX",
      "Tag": "Default",
      "VIP": "10.25.XX.XX",
      "VIPId": "vip-XXX",
      "VPCId": "uvnet-XXX",
      "Zone": "cn-sh2-01"
    }
  ]
}
```





