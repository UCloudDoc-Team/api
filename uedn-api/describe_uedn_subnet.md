# 获取子网列表 - DescribeUEdnSubnet

## 简介

获取子网列表





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUEdnSubnet)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEdnSubnet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **IdcId** | string | 机房ID |No|
| **SubnetId** | string | 子网ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SubnetList** | array[[*SubnetInfo*](#SubnetInfo)] | 子网信息列表 |No|

#### 数据模型


#### SubnetInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SubnetId** | string | 子网ID |**Yes**|
| **SubnetName** | string | 子网名称 |**Yes**|
| **IdcId** | string | 机房ID |**Yes**|
| **CIDR** | string | 子网cidr |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Comment** | string | 备注 |**Yes**|
| **TotalIpCnt** | int | 总ip数 |**Yes**|
| **AvailableIPCnt** | int | 可用ip数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEdnSubnet
&ProjectId=org-xxx
&IdcId=uedn-idc-xxx
&SubnetId=uedn-subnet-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeUEdnSubnetResponse",
  "RetCode": 0,
  "SubnetList": [
    {
      "AvailableIPCnt": 253,
      "CIDR": "10.10.9.0/24",
      "Comment": "igfjPEzM",
      "CreateTime": 1577762217,
      "IdcId": "uedn-idc-xxx",
      "SubnetId": "uedn-subnet-xxx",
      "SubnetName": "test-subnet",
      "TotalIpCnt": 254
    }
  ]
}
```





