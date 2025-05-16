# 获取安全组绑定资源 - DescribeSecGroupResource

## 简介

获取安全组绑资源信息

?> 查询单个安全组绑定的资源（返回资源详细信息），支持分页查询（对绑定的资源分页获取）。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSecGroupResource)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSecGroupResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | int | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SecGroupId** | string | 安全组资源ID。 |No|
| **Limit** | int | 分页查询长度。默认为20 |No|
| **Offset** | int | 分页查询起始位置偏移量。默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*SecGroupResourceInfo*](#SecGroupResourceInfo)] | 详见SecGroupResourceInfo |**Yes**|
| **TotalCount** | int | 安全组绑定的资源总数 |No|

#### 数据模型


#### SecGroupResourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | int | 可用区 |No|
| **SubResourceName** | string | 绑定的虚拟网卡的名称 |No|
| **SubResourceId** | string | 资源绑定的虚拟网卡的ID |No|
| **SubResourceType** | string | 绑定的虚拟网卡的类型，“uni”，虚拟网卡 |No|
| **Name** | string | 名称 |No|
| **PrivateIp** | string | 内网IP |No|
| **ResourceId** | string | 资源ID |No|
| **ResourceType** | string | 资源类型。"unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计，“uni”，虚拟网卡。 |No|
| **Tag** | string | 业务组 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSecGroupResource
&Region=cn-zj
&ProjectId=8
&VPCId=HyexAArD
&SecGroupId.n=VTqSSEeQ
&Limit=8
&Offset=9
```

### 响应示例
    
```json
{
  "Action": "DescribeSecGroupResourceResponse",
  "DataSet": [
    {
      "CreateTime": "FoMZwgfr",
      "Name": "UwordIJs",
      "Remark": "QBoDnpRT",
      "Rule": [
        {
          "Direction": "jNHxLDwL",
          "DstPort": "NpGQxxzK",
          "IPRange": "ucVuYjCx",
          "IPVersion": "rMVegzTz",
          "Priority": "jmnsFfZh",
          "ProtocolType": "jZBVvGxk",
          "Remark": "XCgCJCZq",
          "RuleAction": "rpnbLSKM",
          "RuleId": "UcATLSQb"
        }
      ],
      "SecGroupId": "QqLcgWZc",
      "Tag": "OjmPShak",
      "VPCId": "yuAobWcz"
    }
  ],
  "RetCode": 0,
  "TotalCount": 6
}
```





