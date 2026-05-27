# 查询隧道 - DescribeCETunnel

## 简介

查询隧道






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCETunnel)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCETunnel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPNId** | string | CE 网关 ID |No|
| **VPNTunnelId** | string | 隧道 ID |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 总数 |**Yes**|
| **VPNTunnelInfos** | array[[*VPNTunnelInfo*](#VPNTunnelInfo)] | 隧道信息 |**Yes**|

#### 数据模型


#### VPNTunnelInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **VPNId** | string | CE 网关 ID |No|
| **VPNTunnelId** | string | 隧道 ID |No|
| **Name** | string | 隧道名称 |No|
| **Remark** | string | 备注 |No|
| **CreateTime** | int | 创建时间 |No|
| **IKEConf** | [*IKEConf*](#IKEConf) | IKE 配置信息 |No|
| **IPSecConf** | [*IPSecConf*](#IPSecConf) | IPSec 配置信息 |No|
| **CloseAction** | string | 隧道关闭后动作 |No|
| **BGPConf** | [*BGPConf*](#BGPConf) | BGP 配置信息 |No|
| **Mode** | string | 路由模式 |No|
| **DPDConf** | [*DPDConf*](#DPDConf) | DPD 配置信息 |No|
| **StartAction** | string | 隧道协商动作 |No|

#### IKEConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PreSharedKey** | string | 预共享密钥 |No|
| **Version** | string | 版本 |No|
| **ExchangeMode** | string | 协商模式 |No|
| **EncryptionAlgorithm** | string | 加密算法 |No|
| **AuthenticationAlgorithm** | string | 认证算法 |No|
| **DhGroup** | string | 分组信息 |No|
| **LocalId** | string | 本端标识 |No|
| **RemoteId** | string | 对端标识 |No|
| **SALifeTime** | string | IKE SA的生存周期 |No|

#### IPSecConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CENetwork** | array[string] | 客户网段 |No|
| **Protocol** | string | 安全协议 |No|
| **EncryptionAlgorithm** | string | 加密算法 |No|
| **AuthenticationAlgorithm** | string | 认证算法 |No|
| **PFSDhGroup** | string | 第二阶段协商使用的 Diffie-Hellman 密钥交换算法 |No|
| **SALifeTime** | string | 第二阶段的 SA 的生存周期 |No|
| **SALifetimeBytes** | string | 第二阶段的 SA 的生存周期 |No|

#### BGPConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TunnelCidr** | string | BGP隧道网段 |No|
| **LocalAsn** | int | 本端自治系统号 |No|
| **PeerAsn** | int | 对端自治系统号 |No|
| **LocalIp** | string | 云端BGP地址 |No|
| **PeerIp** | string | 用户端BGP地址 |No|

#### DPDConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | int | 是否开启 DPD |**Yes**|
| **Action** | string | DPD 行为 |**Yes**|
| **Delay** | int | DPD 探测间隔时间 |**Yes**|
| **Timeout** | int | DPD 探测超时时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCETunnel
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cPhzWCSM
&VPNId=NwIBmeCO
&VPNTunnelId=TzGXsJZe
&Offset=8
&Limit=7
```

### 响应示例
    
```json
{
  "Action": "DescribeCETunnelResponse",
  "Message": "pRdXCzZp",
  "RetCode": 0,
  "TotalCount": 9,
  "VPNTunnelInfos": [
    {
      "CloseAction": "HTVuuKpu",
      "CreateTime": 1,
      "IKEConf": {},
      "IPSecConf": {},
      "Name": "KWICNutf",
      "Remark": "MxIeSPzs",
      "VPNId": "ghjjFyaH",
      "VPNTunnelId": "KZUcuUKg"
    }
  ]
}
```





