# 查询CPE绑定的加速线路信息 - DescribeExportLine

## 简介

查询CPE绑定的加速线路信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeExportLine)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeExportLine`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CPEId** | string | CPE资源ID |No|
| **ResourceId** | string | UReach资源ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LineInfos** | array[[*LineInfo*](#LineInfo)] | 线路信息 |No|

#### 数据模型


#### LineInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 名称 |No|
| **Remark** | string | 备注 |No|
| **ResourceId** | string | 线路资源ID |No|
| **InstanceId** | string | 线路资源ID对应的加速线路ID |No|
| **Bandwidth** | int | 带宽大小(Mbps) |No|
| **ChargeType** | string | 付费方式(按月、按年等) |No|
| **PayMode** | string | 计费方式(固定带宽: fixed-bw；流量计费：traffic) |No|
| **FromRegion** | string | 入口地域 |No|
| **FromRegionName** | string | 入口地域名称 |No|
| **ToRegion** | string | 出口地域 |No|
| **ToRegionName** | string | 出口地域名称 |No|
| **IP** | array[string] |  |No|
| **Status** | string | 线路是否绑定CPE；"1"：已绑定；"0"未绑定 |No|
| **CreateTime** | int | 创建时间 |No|
| **ExpireTime** | int | 到期时间 |No|
| **CPEIds** | array[string] | 线路绑定的CPE资源ID |No|
| **PkgType** | string | 套餐类型 |No|
| **IpType** | string | IP类型 |No|
| **InstanceStatus** | string | 是否过期(normal/expire) |No|
| **Socks** | [*SocksInfo*](#SocksInfo) |  |No|
| **Source** | array[string] | 源IP地址 |No|

#### SocksInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Addr** | string |  |No|
| **Port** | int |  |No|
| **Account** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeExportLine
&ProjectId=WIrVbEjq
&CPEId=VTKomNmm
&ResourceId=QlHbVjWQ
```

### 响应示例
    
```json
{
  "Action": "DescribeExportLineResponse",
  "LineInfos": [
    {
      "Bandwidth": 1,
      "ExpireTime": 2,
      "FromRegion": "vncTxGOf",
      "IP": [
        "ioeIljnG"
      ],
      "Name": "XxWsPZje",
      "PayMode": "ToSyENwj",
      "Status": "whrozgeR",
      "ToRegion": "fQfdghxB"
    }
  ],
  "Message": "fpcAziPK",
  "RetCode": 0
}
```





