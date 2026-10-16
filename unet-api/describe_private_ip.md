# 获取辅助IP信息 - DescribePrivateIP

## 简介

获取资源绑定的内网IP信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePrivateIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePrivateIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | VPC的ID |No|
| **SubnetId** | string | 子网的ID |No|
| **ObjectId** | string | 虚拟网卡的资源ID;  ObjectId为空时，则获取项目下所有的虚拟网卡主辅IP信息 |No|
| **Limit** | int | 获取信息数量 ，默认20；不允许为0 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 返回资源数量 |**Yes**|
| **DataSet** | array[[*DescribeSecondaryIPDataSet*](#DescribeSecondaryIPDataSet)] | 辅助IP的详细信息 |**Yes**|

#### 数据模型


#### DescribeSecondaryIPDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PrivateIPType** | string | 内网IP类型；枚举值：PrimaryIP：主内网IP，SecondaryIP：辅助内网IP |No|
| **VPCID** | string | VPCID  |No|
| **EIP** | string | 外网IP |No|
| **ResourceID** | string | 资源ID |No|
| **ResourceName** | string | 资源名称 |No|
| **PrivateIP** | string | 内网IP |No|
| **SubnetID** | string | 子网ID  |No|
| **EIPId** | string | EIP资源ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePrivateIP
&Region=cn-bj2
&ProjectId=org-XXXXX
&VPCId=vnet-XXXXX
&SubnetId=subnet-XXXXX
&ObjectId=uni-XXXXX
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribePrivateIPResponse",
  "DataSet": [
    {
      "EIP": "X.X.X.X",
      "EIPId": "eip-XXXXX",
      "PrivateIP": "X.X.X.X",
      "PrivateIPType": "PrimaryIP",
      "ResourceID": "uni-XXXXX",
      "ResourceName": "test-1",
      "SubnetID": "subnet-XXXXX",
      "VPCID": "uvnet-XXXXX"
    },
    {
      "EIP": "",
      "EIPId": "",
      "PrivateIP": "X.X.X.X",
      "PrivateIPType": "SecondaryIP",
      "ResourceID": "uni-XXXXX",
      "ResourceName": "test-1",
      "SubnetID": "subnet-XXXXX",
      "VPCID": "uvnet-XXXXX"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





