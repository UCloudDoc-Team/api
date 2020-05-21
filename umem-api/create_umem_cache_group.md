# 创建单机Memcache - CreateUMemcacheGroup

## 简介

创建单机Memcache






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUMemcacheGroup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUMemcacheGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Name** | string | 请求创建组的名称 范围[6-60] |**Yes**|
| **Size** | int | 每个节点的内存大小,单位GB,默认1GB 目前仅支持1/2/4/8/16/32这几档 |No|
| **ConfigId** | string | 配置ID,目前仅支持默认配置id 默认配置id:"9a891891-c245-4b66-bce8-67e59430d67c" |No|
| **Version** | string | Memcache版本信息,默认为1.4.31 |No|
| **ChargeType** | string | 计费模式，Year , Month, Dynamic 默认: Month |No|
| **Quantity** | int | 购买时长，默认为1 |No|
| **Tag** | string | 业务组 默认：Default |No|
| **Protocol** | string |  |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupId** | string | 创建的组ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUMemcacheGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&Name=djdj_XXXXX
&SubnetId=qVnAwdPw
&Protocol=fmwGhgdR
```

### 响应示例
    
```json
{
  "Action": "CreateUMemcacheGroupResponse",
  "GroupId": "00f9868c-c7f5-4852-9eac-d200b678f0e1",
  "RetCode": 0
}
```





