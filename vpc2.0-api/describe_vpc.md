# 获取VPC信息 - DescribeVPC

## 简介

获取VPC信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVPC)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVPC`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCIds.N** | string | VPCId |No|
| **Tag** | string | 业务组名称 |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 数据分页值 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*VPCInfo*](#VPCInfo)] | vpc信息，具体结构见下方VPCInfo |No|
| **TotalCount** | int |  |No|

#### 数据模型


#### VPCInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NetworkInfo** | array[[*VPCNetworkInfo*](#VPCNetworkInfo)] | vpc地址空间信息，详见VPCNetworkInfo |**Yes**|
| **SubnetCount** | int | 子网数 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **UpdateTime** | int | 更新时间 |**Yes**|
| **Tag** | string | 业务组 |**Yes**|
| **Name** | string | VPC名称 |**Yes**|
| **VPCType** | string | DefaultVPC 默认VPC，DefinedVPC，自定义VPC      |No|
| **VPCId** | string | VPC资源ID |No|
| **Network** | array[string] | VPC网段 |No|
| **IPv6Network** | string | VPC关联的IPv6网段 |No|
| **OperatorName** | string | VPC关联的IPv6网段所属运营商 |No|

#### VPCNetworkInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Network** | string | vpc地址空间 |No|
| **SubnetCount** | int | 地址空间中子网数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeVPC
&ProjectId=org-xxx
&Region=cn-sh2
&VPCIds.0=uvnet-xxx
&Offset=9
&Limit=9
```

### 响应示例
    
```json
{
  "Action": "DescribeVPCResponse",
  "DataSet": [
    {
      "CreateTime": 1514313728,
      "Name": "DefaultVPC",
      "Network": [
        "10.44.x.0/16"
      ],
      "NetworkInfo": [
        {
          "Network": "10.44.x.0/16",
          "SubnetCount": 1
        }
      ],
      "SubnetCount": 1,
      "Tag": "Default",
      "UpdateTime": 1514313728,
      "VPCId": "uvnet-xxx"
    },
    {
      "CreateTime": 1533891436,
      "Name": "testabc",
      "Network": [
        "192.168.x.0/16",
        "10.0.0.0/8"
      ],
      "NetworkInfo": [
        {
          "Network": "192.168.x.0/16",
          "SubnetCount": 1
        },
        {
          "Network": "10.0.0.0/8",
          "SubnetCount": 1
        }
      ],
      "Remark": "",
      "SubnetCount": 2,
      "Tag": "Default",
      "UpdateTime": 1533891438,
      "VPCId": "uvnet-xxxxx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





