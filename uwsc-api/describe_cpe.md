# 查询 CPE 信息 - DescribeCPE

## 简介

查询 CPE 信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCPE)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCPE`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **CPEId** | string | cpe id |No|
| **Label** | string | 标签：Access、Network |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CPEInfos** | array[[*CPEInfo*](#CPEInfo)] | cpe 详情 |No|

#### 数据模型


#### CPEInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CPEId** | string | 资源ID |No|
| **CPEName** | string | 资源名称 |No|
| **Remark** | string | 备注 |No|
| **DeviceTypeName** | string | 设备型号 |No|
| **Vendor** | string | 供应商 |No|
| **PopGwId** | array[string] | 绑定的UWAN资源ID |No|
| **Sn** | string | 设备SN |No|
| **Status** | int | 状态 |No|
| **ConfUpdateTime** | int | 配置更新时间 |No|
| **Ports** | array[string] | 端口 |No|
| **LinkNum** | int | 链路数量 |No|
| **CreateTime** | int | 创建时间 |No|
| **LineStatus** | string | 是否与线路绑定 |No|
| **ResourceIds** | array[string] | 绑定的UReach线路资源ID |No|
| **UseTime** | int | 有效使用时间(天) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCPE
&ProjectId=UOrTIjzr
&RequestID=HgjZATtq
&CpeId=XGSgRreH
&Sn=RNpHHtvO
&Label=seYMmdVp
```

### 响应示例
    
```json
{
  "Action": "DescribeCPEResponse",
  "ConfUpdateTime": "SKBpJSSK",
  "CpeName": "BVhUyuKT",
  "CreateTime": 2,
  "DeviceTypeName": "HGQaAXbm",
  "IsBind": false,
  "LinkNum": 5,
  "Message": "yBoiprcV",
  "PopgwId": "SOYeXahb",
  "Ports": "nbftUARD",
  "Remark": "hjhDiPdZ",
  "RetCode": 0,
  "Sn": "hbtfxWms",
  "Status": 2,
  "Vendor": "gceoCYgk"
}
```





