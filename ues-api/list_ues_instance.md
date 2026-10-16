# 实例列表 - ListUESInstance

## 简介

获取实例列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUESInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUESInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 返回数据长度, 默认为30 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | array[[*ClusterInfo*](#ClusterInfo)] | 实例信息列表 |**Yes**|
| **TotalCount** | int | 实例个数 |**Yes**|

#### 数据模型


#### ClusterInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **BusinessId** | string | 项目组ID标识 |**Yes**|
| **ChargeType** | string | 计费类型，默认为Month |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ExpireTime** | int | 失效时间 |**Yes**|
| **NodeCount** | int | 节点个数，默认为集群大小 |**Yes**|
| **RunTime** | int | 实例运行时长 |**Yes**|
| **AppVersion** | string | 应用服务版本号 |**Yes**|
| **State** | string | 实例状态 |**Yes**|
| **InstanceId** | string | 实例资源ID |**Yes**|
| **InstanceName** | string | 实例名称 |**Yes**|
| **AppName** | string | 应用名称 |**Yes**|
| **UESInstanceId** | string | 服务集群ID标识（弃用） |No|
| **UESInstanceName** | string | 服务集群名称（弃用） |No|
| **ServiceVersion** | string | 服务版本号（弃用） |No|
| **SubnetId** | string | 子网ID标识 |No|
| **Tag** | string | 业务组 |No|
| **VPCId** | string | VPCID标识 |No|
| **Vip** | string | VIP地址信息 |No|
| **IsSecGroup** | boolean | 是否开启安全组 |No|
| **MultiZones** | array[string] | 多可用区 |No|
| **Resizable** | boolean | 是否支持改配 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUESInstance
&Region=cn-zj
&Zone=cn-zj-01
&Offset=5
&Limit=4
&VPCId=RolneVaa
&SubnetId=jOQqKmRo
&BusinessId=JrwewLQz
```

### 响应示例
    
```json
{
  "Action": "ListUESInstanceResponse",
  "ClusterSet": [
    {
      "BusinessId": "WPWmJkjN",
      "CreateTime": 4,
      "ExpireTime": 2,
      "NodeCount": 6,
      "RunTime": 5,
      "State": "cCXunFVC",
      "SubnetId": "JraNOHvs",
      "UESInstanceId": "zOZuYWEu",
      "UESInstanceName": "ibaADTdd",
      "VPCId": "zdeQmEss",
      "Zone": "zCnNgWTq"
    },
    {
      "BusinessId": "tPbLJpqW",
      "CreateTime": 7,
      "ExpireTime": 3,
      "NodeCount": 5,
      "RunTime": 6,
      "State": "qsQmBsvs",
      "SubnetId": "zZUeFYCg",
      "UESInstanceId": "zTaLUgJZ",
      "UESInstanceName": "LcHmHPqL",
      "VPCId": "eBXtFMuW",
      "Zone": "QbwPHeOf"
    },
    {
      "BusinessId": "usmPNYTW",
      "CreateTime": 7,
      "ExpireTime": 2,
      "NodeCount": 7,
      "RunTime": 2,
      "State": "NBTCrJWq",
      "SubnetId": "PlrCyOoH",
      "UESInstanceId": "ywNFFZbs",
      "UESInstanceName": "WnqtGAex",
      "VPCId": "frVZevkb",
      "Zone": "sycGkseG"
    },
    {
      "BusinessId": "WXEQWAei",
      "CreateTime": 7,
      "ExpireTime": 7,
      "NodeCount": 4,
      "RunTime": 8,
      "State": "IzKYUzbr",
      "SubnetId": "RWEEcihF",
      "UESInstanceId": "wMglRzTR",
      "UESInstanceName": "HikTZTzr",
      "VPCId": "QwHKbynu",
      "Zone": "rOIhMdcs"
    },
    {
      "BusinessId": "TtzcEKdK",
      "CreateTime": 1,
      "ExpireTime": 1,
      "NodeCount": 7,
      "RunTime": 2,
      "State": "HtvtjCLU",
      "SubnetId": "HQvzQoPo",
      "UESInstanceId": "EAYxGOva",
      "UESInstanceName": "ByMceqMT",
      "VPCId": "xRKWyKaF",
      "Zone": "WeInikev"
    },
    {
      "BusinessId": "TZSHRNGV",
      "CreateTime": 8,
      "ExpireTime": 2,
      "NodeCount": 5,
      "RunTime": 3,
      "State": "rwWAwqgN",
      "SubnetId": "ijdmBZsz",
      "UESInstanceId": "HwXNUBjn",
      "UESInstanceName": "aoJGmgyh",
      "VPCId": "QeOGrPWr",
      "Zone": "eWOpiRCu"
    },
    {
      "BusinessId": "UMyVOJQn",
      "CreateTime": 2,
      "ExpireTime": 4,
      "NodeCount": 5,
      "RunTime": 8,
      "State": "YYWLqqBk",
      "SubnetId": "uKcDEXwB",
      "UESInstanceId": "mJNtGDxb",
      "UESInstanceName": "bHfimENM",
      "VPCId": "ARPhYMQA",
      "Zone": "mUnRxJsM"
    },
    {
      "BusinessId": "VdbZsCKn",
      "CreateTime": 1,
      "ExpireTime": 8,
      "NodeCount": 9,
      "RunTime": 1,
      "State": "uuHphiCy",
      "SubnetId": "ysWPBIiD",
      "UESInstanceId": "XJyGpzYA",
      "UESInstanceName": "KFIhouyj",
      "VPCId": "aVPXLiNS",
      "Zone": "BRjckNDT"
    },
    {
      "BusinessId": "IKnwkawG",
      "CreateTime": 8,
      "ExpireTime": 5,
      "NodeCount": 9,
      "RunTime": 1,
      "State": "hfnbhUnf",
      "SubnetId": "uAZXVDGM",
      "UESInstanceId": "aRTxAjQP",
      "UESInstanceName": "SQJojSLJ",
      "VPCId": "BUqSQfIT",
      "Zone": "EcfVBAaM"
    }
  ],
  "Message": "ePkiOQwQ",
  "RetCode": 0,
  "TotalCount": 1
}
```





