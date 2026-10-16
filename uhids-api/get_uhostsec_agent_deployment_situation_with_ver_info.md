# 列出当前项目的主机安装信息(包括付费版本信息) - GetUhostsecAgentDeploymentSituationWithVerInfo

## 简介

获取当前项目的主机安装信息，包括IP，当前付费版本等信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUhostsecAgentDeploymentSituationWithVerInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InfoList** | array[[*HostAgentStatusInfo*](#HostAgentStatusInfo)] | 主机信息 |No|
| **TotalNum** | int | 主机总数 |No|
| **InstallNum** | int | 已安装UHIDS的主机数 |No|
| **UninstallNum** | int | 未安装UHIDS的主机数 |No|

#### 数据模型


#### HostAgentStatusInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |**Yes**|
| **Ip** | array[string] | 主机IP列表 |**Yes**|
| **UHostId** | string | uhost资源短ID |**Yes**|
| **AgentId** | string | UHIDS的Agent识别ID |**Yes**|
| **Installed** | boolean | 是否已经安装 |**Yes**|
| **NowVer** | int | 此主机当前UHIDS版本信息 |**Yes**|
| **SetVer** | int | 用户设置此主机UHIDS版本信息 |**Yes**|
| **HostName** | string | uhost的备注名 |**Yes**|
| **NICs** | array[[*NIC*](#NIC)] | 网卡信息列表 |**Yes**|
| **OsName** | string | 系统版本 |No|

#### NIC

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | 网卡ip |No|
| **Mac** | string | 网卡mac |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUhostsecAgentDeploymentSituationWithVerInfo
&ProjectId=KXhzaqMC
&Installed=false
&Uninstalled=false
```

### 响应示例
    
```json
{
  "Action": "GetUhostsecAgentDeploymentSituationWithVerInfoResponse",
  "InfoList": [
    {
      "AgentId": "rljHiCId",
      "HostName": "IHTapxQz",
      "Installed": true,
      "Ip": [
        "yfsHDWMF"
      ],
      "NICs": [
        {
          "IP": "rPpLjDbt",
          "Mac": "PdrijsQk"
        }
      ],
      "NowVer": 6,
      "SetVer": 7,
      "UHostId": "XQtxROXt",
      "Zone": "bufXLCIv"
    }
  ],
  "InstallNum": 1,
  "RetCode": 0,
  "TotalNum": 4,
  "UninstallNum": 8
}
```





