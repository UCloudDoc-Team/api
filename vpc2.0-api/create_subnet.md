# 创建子网 - CreateSubnet

## 简介

创建子网






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateSubnet)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateSubnet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **VPCId** | string | VPC资源ID |**Yes**|
| **Subnet** | string | 子网网络地址，例如192.168.0.0 |**Yes**|
| **Netmask** | int | 子网网络号位数，默认为24 |No|
| **SubnetName** | string | 子网名称，默认为Subnet |No|
| **Tag** | string | 业务组名称，默认为Default |No|
| **Remark** | string | 备注 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SubnetId** | string | 子网ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateSubnet
&ProjectId=org-XXXXX
&Region=cn-sh2
&VPCId=vnet-XXXX
&Subnet=10.1.1.0
&Netmask=24
&SubnetName=test
&Tag=test
&Remark=test
&BusinessId=test
```

### 响应示例
    
```json
{
  "Action": "CreateSubnetResponse",
  "RetCode": 0,
  "SubnetId": "subnet-XXXXX"
}
```





