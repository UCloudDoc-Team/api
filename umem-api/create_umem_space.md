# 创建内存空间 - CreateUMemSpace

## 简介

创建UMem内存空间






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUMemSpace)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUMemSpace`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 内存大小, 单位:GB, 范围[1\~1024] |**Yes**|
| **Name** | string | 空间名称,长度(6<=size<=63) |**Yes**|
| **Protocol** | string | 协议:memcache, redis (默认redis).注意:redis无single类型 |No|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |No|
| **ChargeType** | string | Year , Month, Dynamic 默认: Month |No|
| **Quantity** | int | 购买时长 默认: 1 |No|
| **VPCId** | string | VPC的ID |No|
| **SubnetId** | string | 子网ID |No|
| **Tag** | string |  |No|
| **Password** | string | URedis密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，举例如下：# echo -n Password1 \| base64UGFzc3dvcmQx。 |No|
| **SlaveZone** | string | 跨机房UDRedis，slave所在可用区（必须和Zone在同一Region，且不可相同） |No|
| **BlockCnt** | int | 分片个数 |No|
| **ClusterMode** | string | 是否是cluster模式（参数为cluster创建redis cluster，其他参数或者不传该参数仍然创建老版本分布式） |No|
| **Version** | string | 分布式分片版本（默认版本是4.0，其他版本见DescribeUDRedisBlockVersion） |No|
| **HighPerformance** | boolean | 是否创建性能增强性。默认为false，或者不填，填true为性能增强型。 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SpaceId** | string | 创建内存空间ID列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUMemSpace
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=16
&Name=memfbs_XXXXXX
&Tag=rWEhrBRd
&Password=EodyPYWL
&Password=VzEIaMAN
&SlaveZone=ptGhogJa
&VPCId=eKWChJCJ
&SubnetId=NBKWNfXD
&BlockCnt=4
&ClusterMode=FZTxNVzD
&Version=WWTSLAYj
&HighPerformance=false
```

### 响应示例
    
```json
{
  "Action": "CreateUMemSpaceResponse",
  "RetCode": 0,
  "SpaceId": "umem-opqmXXXX"
}
```





