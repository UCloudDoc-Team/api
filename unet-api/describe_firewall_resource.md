# 获取防火墙绑定资源 - DescribeFirewallResource

## 简介

获取防火墙组所绑定资源的外网IP






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeFirewallResource)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeFirewallResource`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **FWId** | string | 防火墙ID |**Yes**|
| **Limit** | int | 返回数据长度，默认为20，最大1000 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceSet** | array[[*ResourceSet*](#ResourceSet)] | 资源列表，见 ResourceSet |No|
| **TotalCount** | int | 绑定资源总数 |No|

#### 数据模型


#### ResourceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | int | 可用区 |No|
| **SubResourceName** | string | 资源绑定的虚拟网卡的名称 |**Yes**|
| **SubResourceId** | string | 资源绑定的虚拟网卡的ID |**Yes**|
| **SubResourceType** | string | 资源绑定的虚拟网卡的类型，“uni”，虚拟网卡。 |**Yes**|
| **Name** | string | 名称 |No|
| **PrivateIP** | string | 内网IP |No|
| **Remark** | string | 备注 |No|
| **ResourceID** | string | 绑定该防火墙的资源id |No|
| **ResourceType** | string | 绑定防火墙组的资源类型。"unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计，“uni”，虚拟网卡。 |No|
| **Status** | int | 状态 |No|
| **Tag** | string | 业务组 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeFirewallResource
&ProjectId=org-xxx
&Region=xxx
&FWId=fw-xxx
&Limit=20
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "DescribeFirewallResourceResponse",
  "ResourceSet": [
    {
      "Name": "hc_host",
      "PrivateIP": "10.23.XX.XX",
      "Remark": "",
      "ResourceID": "uhost-XXXXXX",
      "ResourceType": "uhost",
      "Status": 1,
      "Tag": "Default",
      "Zone": 8200
    }
  ],
  "RetCode": 0,
  "TotalCount": 6
}
```





