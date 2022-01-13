# 拉取UInfluxdb实例列表 - DescribeUInfluxdbInstance

## 简介

拉取UInfluxdb实例列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUInfluxdbInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUInfluxdbInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 分页显示起始偏移位置，列表操作则指定 |No|
| **Limit** | int | 分页显示数量，列表操作则指定 |No|
| **UInfluxdbId** | string | 指定id的话，会拉取该实例信息，否则拉取该帐号所有信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UInfluxdbDataSet*](#UInfluxdbDataSet)] | UInfluxdb实例信息 |**Yes**|

#### 数据模型


#### UInfluxdbDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | UInfluxdb实例所在可用区 |No|
| **VPCId** | string | VPC的ID |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **Tag** | string | 业务组信息 |**Yes**|
| **AccountName** | string | 账户名 |**Yes**|
| **UsedSize** | int | 硬盘使用量 |**Yes**|
| **UInfluxdbId** | string | 实例id |No|
| **Name** | string | 实例名称 |No|
| **VirtualIP** | string | 实例ip |No|
| **Port** | int | 实例端口 |No|
| **State** | string | 实例状态 |No|
| **CPULimit** | int | 实例核数 |No|
| **MemoryLimit** | int | 实例内存 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpiredTime** | int | 修改时间 |No|
| **ChargeType** | string | 付费类型，可选值如下: Year: 按年付费 Month: 按月付费 Dynamic: 按需付费(单位: 小时) Trial: 免费试用 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUInfluxdbInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=iJltqTIQ
&Offset=5
&Limit=8
&UInfluxdbId=IeTiBGpJ
```

### 响应示例
    
```json
{
  "Action": "DescribeUInfluxdbInstanceResponse",
  "DataSet": "VXRFQlal",
  "RetCode": 0
}
```





