# 创建云联网 - CreateUGN

## 简介

创建云联网






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGN)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | UGN名称 |No|
| **Remark** | string | 备注 |No|
| **Networks.N.NetworkID** | string | 网络实例 ID，如 uvnet-xxxx |No|
| **Networks.N.Type** | string | 网络实例类型，枚举值：VPC/UCVR/... |No|
| **Networks.N.Region** | string | 网络实例所属地域，如 cn-sh2 |No|
| **Networks.N.OrgName** | string | 网络实例所属项目名，如 org-xxx |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGNID** | string | UGN ID |No|
| **Networks** | array[[*Network*](#Network)] | 网络实例列表 |No|

#### 数据模型


#### Network

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 网络实例所在地域 |**Yes**|
| **NetworkID** | string | 网络实例的ID，如 vnet-xxxxx |**Yes**|
| **Name** | string | 网络实例名称 |**Yes**|
| **Type** | string | 网络实例类型：VPC/UCVR/... |**Yes**|
| **OrgName** | string | 网络实例所在项目名 |**Yes**|
| **CompanyID** | int | 网络实例所属公司ID |**Yes**|
| **RegionID** | int | 网络实例所在地域ID |No|
| **OrgID** | int | 网络实例所在项目的ID |No|
| **VNI** | int | 网络实例的唯一标识，如 vpc 的 tunnel_id |No|
| **InsertTime** | int | 创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGN
&ProjectId=HtkTGJAF
&Name=HDgqVUkq
&Remark=lrNklkCW
&Networks.N.NetworkID=asaCbwIt
&Networks.N.Type=wJNiJeMH
&Networks.N.Region=DIvWCBGu
&Networks.N.OrgName=zWscmBfN
```

### 响应示例
    
```json
{
  "Action": "CreateUGNResponse",
  "Message": "mSZbBqrW",
  "Networks": [
    {
      "CompanyID": 4,
      "InsertTime": 2,
      "Name": "mrBaQbPr",
      "NetworkID": "vBqMphpg",
      "OrgID": 9,
      "OrgName": "lhvuQWjE",
      "Region": "PUOLsPuG",
      "RegionID": 1,
      "Type": "AOMdtzyw",
      "VNI": 4
    }
  ],
  "RetCode": 0,
  "UGNID": "RidmbTLC"
}
```





