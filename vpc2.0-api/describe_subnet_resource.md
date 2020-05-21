# 展示子网资源 - DescribeSubnetResource

## 简介

展示子网资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSubnetResource)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSubnetResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SubnetId** | string | 子网id |**Yes**|
| **ResourceType** | string | 资源类型，默认为全部资源类型。枚举值为：UHOST，云主机；PHOST，物理云主机；ULB，负载均衡；UHADOOP_HOST，hadoop节点；UFORTRESS_HOST，堡垒机；UNATGW，NAT网关；UKAFKA，Kafka消息队列；UMEM，内存存储；DOCKER，容器集群；UDB，数据库；UDW，数据仓库；VIP，内网VIP. |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 单页返回数据长度，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |No|
| **DataSet** | array[[*SubnetResource*](#SubnetResource)] | 返回数据集，请见SubnetResource |No|

#### 数据模型


#### SubnetResource

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 名称 |No|
| **ResourceId** | string | 资源Id |No|
| **ResourceType** | string | 资源类型。对应的资源类型：UHOST，云主机；PHOST，物理云主机；ULB，负载均衡；UHADOOP_HOST，hadoop节点；UFORTRESS_HOST，堡垒机；UNATGW，NAT网关；UKAFKA，分布式消息系统；UMEM，内存存储；DOCKER，容器集群；UDB，数据库；UDW，数据仓库；VIP，内网VIP. |No|
| **IP** | string | 资源ip |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSubnetResource
&Region=cn-sh2
&ProjectId=org-XXXX
&SubnetId=subnet-XXXXX
&ResourceType=VIP
&Offset=1
&Limit=5
```

### 响应示例
    
```json
{
  "Action": "DescribeSubnetResourceResponse",
  "DataSet": [
    {
      "IP": "10.23.XX.25",
      "Name": "VIP",
      "ResourceId": "vip-XXXX",
      "ResourceType": "VIP"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





