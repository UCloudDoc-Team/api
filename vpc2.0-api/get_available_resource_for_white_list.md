# 获取NAT网关可添加白名单的资源 - GetAvailableResourceForWhiteList

## 简介

获取NAT网关可添加白名单的资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAvailableResourceForWhiteList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAvailableResourceForWhiteList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NATGWId** | string | NAT网关Id |**Yes**|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 数据分页值, 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*GetAvailableResourceForWhiteListDataSet*](#GetAvailableResourceForWhiteListDataSet)] | 返回白名单列表的详细信息 |**Yes**|
| **TotalCount** | int | 白名单资源列表的总的个数 |**Yes**|

#### 数据模型


#### GetAvailableResourceForWhiteListDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源类型Id |**Yes**|
| **ResourceName** | string | 资源名称 |**Yes**|
| **PrivateIP** | string | 资源的内网Ip |**Yes**|
| **ResourceType** | string | 资源类型。"uhost"：云主机； "upm"，物理云主机； "hadoophost"：hadoop节点； "fortresshost"：堡垒机： "udockhost"，容器 |**Yes**|
| **SubResourceName** | string | 资源绑定的虚拟网卡的实例名称 |**Yes**|
| **VPCId** | string | 资源所属VPCId |**Yes**|
| **SubnetworkId** | string | 资源所属子网Id |**Yes**|
| **SubResourceId** | string | 资源绑定的虚拟网卡的实例ID |No|
| **SubResourceType** | string | 资源绑定的虚拟网卡的实例类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAvailableResourceForWhiteList
&Region=xxx
&ProjectId=xxx
&NATGWId=CuqLxGDE
&Offset=7
&Limit=8
```

### 响应示例
    
```json
{
  "Action": "GetAvailableResourceForWhiteListResponse",
  "DataSet": [
    {
      "PrivateIP": "xxxx",
      "ResourceId": "xxxx",
      "ResourceType": "xxxx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





