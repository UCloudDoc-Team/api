# zone下所有域名的rr记录 - DescribeUDNSDomain

## 简介

zone下所有域名的rr记录






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDNSDomain)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDNSDomain`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **DNSZoneName** | string | zone名称 |**Yes**|
| **VPCId** | string | VPI资源ID |**Yes**|
| **Offset** | int | 查询数量偏移 |No|
| **Limit** | int | 返回数量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RecordInfos** | array[[*RecordInfo*](#RecordInfo)] | 查询记录 |**Yes**|
| **TotalCount** | int | 总条数 |**Yes**|

#### 数据模型


#### RecordInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RecordId** | string | 域名记录资源ID |**Yes**|
| **Name** | string | 主机记录 |**Yes**|
| **Type** | string | 记录类型 |**Yes**|
| **ValueSet** | array[[*ValueSet*](#ValueSet)] | 数值组 |**Yes**|
| **ValueType** | string | 记录策略，标准或随机应答 |**Yes**|
| **TTL** | int | TTL值，单位为秒 |**Yes**|
| **Remark** | string | 记录备注信息 |**Yes**|

#### ValueSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Data** | string | 主机记录 |**Yes**|
| **Weight** | int | 权重 |**Yes**|
| **IsEnabled** | int | 是否启用 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDNSDomain
&Region=cn-zj
&ProjectId=VazeIsAc
&DNSZoneName=SmOFxzQi
&VPCId=mndbhyUK
&Offset=1
&Limit=2
```

### 响应示例
    
```json
{
  "Action": "DescribeUDNSDomainResponse",
  "RecordInfos": [
    {
      "Name": "tkCApOvq",
      "RecordId": "yRQSXDut",
      "Remark": "vyElewiS",
      "TTL": 8,
      "Type": "zVcKNwZd",
      "ValueSet": [
        {
          "Data": "gGjEmoub",
          "IsEnabled": 9,
          "Weight": 4
        }
      ],
      "ValueType": "MOJvQMjj"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





