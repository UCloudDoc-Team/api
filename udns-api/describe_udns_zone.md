# 获取域名信息 - DescribeUDNSZone

## 简介

获取域名信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDNSZone)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDNSZone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **DNSZoneIds.N** | string | 域名资源ID |No|
| **Limit** | int | 数据分页值, 默认为20 |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 符合查询条件的域名数量 |**Yes**|
| **DNSZoneInfos** | array[[*ZoneInfo*](#ZoneInfo)] | 域名资源信息 |No|

#### 数据模型


#### ZoneInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DNSZoneName** | string | 域名名称 |**Yes**|
| **Tag** | string | 业务组 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **IsRecursionEnabled** | string | 是否支持迭代。枚举值,"enable",支持迭代; "disable",不支持迭代 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ExpireTime** | int | 过期时间 |**Yes**|
| **ChargeType** | string | 计费类型（Dynamic、Month、Year） |**Yes**|
| **IsAutoRenew** | string | 是否开启自动续费（Yes No） |**Yes**|
| **RecordInfos** | array[string] | 记录相关ID |No|
| **VPCInfos** | array[[*VPCInfo*](#VPCInfo)] | 绑定的VPC信息 |No|

#### VPCInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VPCId** | string | VPC ID |No|
| **VPCProjectId** | string | VPC所属项目ID |No|
| **Name** | string | VPC名称 |No|
| **Network** | array[string] | VPC地址空间 |No|
| **VPCType** | string | VPC类型：Normal 公有云 Hybrid 托管云 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDNSZone
&Region=cn-zj
&ProjectId=pjyxtfGa
&DNSZoneIds.n=fNWcjBlJ
&Limit=7
&Offset=4
```

### 响应示例
    
```json
{
  "Action": "DescribeUDNSZoneResponse",
  "DNSZoneInfos": [
    {
      "ChargeType": "rLvVRRkH",
      "CreateTime": 2,
      "DNSZoneName": "aQlOZCUk",
      "ExpireTime": 2,
      "IsAutoRenew": "GtbNDZZp",
      "IsRecursionEnabled": "PapLNxnE",
      "RecordInfos": "RIPPjBYL",
      "Remark": "MdLLBszW",
      "Tag": "FIjdolyS",
      "VPCInfos": [
        {
          "Name": "bUWguZkb",
          "Network": [
            "MvWnAlnS"
          ],
          "VPCId": "NOmAbXZm",
          "VPCProjectId": "klzERHqX",
          "VPCType": "bFrWctwm"
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





