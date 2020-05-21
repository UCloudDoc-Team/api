# 获取直播加速域名信息列表 - GetUliveDomainDetail

## 简介

获取直播加速域名信息列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUliveDomainDetail)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUliveDomainDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DomainId.N** | string | 创建域名时候生成的domain_uid 可以传递多个，n代表自然数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的直播加速个数 |**Yes**|
| **ChargeType** | string | 表示当前的计费方式，traffic代表按流量包计费，bandwidth按带宽付费 |**Yes**|
| **LastChargeType** | string | 表示最后一次切换的计费方式，traffic代表按流量包计费，bandwidth按带宽付费 |**Yes**|
| **Arrearage** | array[int] | 是否欠费，1-国内流量欠费 2-国外流量欠费 3-国内日带宽欠费 4-国外日带宽欠费 (线下按月带宽不需要) |No|
| **DomainSet** | array[[*DomainSet*](#DomainSet)] | 获取的域名信息，具体参考下面DomainSet |No|

#### 数据模型


#### DomainSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 域名Id，创建直播加速生成的Id |**Yes**|
| **LiveName** | string | 直播加速名称 |**Yes**|
| **PublishDomain** | string | 推流域名(拉流加速时，该字段为空) |**Yes**|
| **PublishCname** | string | 推流Cname域名，客户推流域名需要CNAME到该域名(拉流加速时，该字段为空) |**Yes**|
| **AccessPoint** | string | 接入点 |**Yes**|
| **CreatTime** | int | 创建时间，格式：unix时间戳 |**Yes**|
| **DomainInfoSet** | array[[*DomainInfoSet*](#DomainInfoSet)] | 播放域名信息列表，参考DomainInfoSet |**Yes**|
| **Status** | string | 加速状态。checking：配置中；enabled：加速中；failed：失败；deleting：删除中；disabling：禁用中；disabled：禁用 |No|
| **SourceIp** | string | 源站域名或ip，如不为空，则为拉流域名；如为空则为推流域名 |No|
| **RecordStatus** | string | 录制状态。disabled:未开启；checking：配置中；enabled：已开启；deleting：关闭中；unsupported：不支持 |No|
| **RecordBucket** | string | 存储录制文件的bucket名称。 |No|
| **RecordCallbackUrl** | string | 用户的录制回调url地址。 |No|

#### DomainInfoSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **Cname** | string | CDN域名，客户CNAME到该域名播放 |**Yes**|
| **Type** | string | 播放域名支持协议类型 rtmp/hdl、hls |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUliveDomainDetail
&ProjectId=org-xxx
```

### 响应示例
    
```json
{
  "Action": "GetUliveDomainDetailResponse",
  "Arrearage": [],
  "ChargeType": "traffic",
  "DomainSet": [
    {
      "AccessPoint": "test",
      "CreateTime": 1529996332,
      "DomainId": "ulive-xxx",
      "DomainInfoSet": [
        {
          "Cname": "62a31d8f.rtmp.ucloud.com.cn",
          "Domain": "rtmp.ashe.ucloud.com.cn",
          "Type": "rtmp/hdl"
        },
        {
          "Cname": "62a31d8f.hls.ucloud.com.cn",
          "Domain": "hls.ashe.ucloud.com.cn",
          "Type": "hls"
        }
      ],
      "LiveName": "live111",
      "PublishCname": "62a31d8f.publish.ucloud.com.cn",
      "PublishDomain": "ashe.ucloud.com.cn",
      "RecordBucket": "",
      "RecordCallbackUrl": "",
      "RecordStatus": "disabled",
      "SourceIp": "",
      "Status": "enabled"
    }
  ],
  "LastChargeType": "traffic",
  "LimitMax": 3,
  "RetCode": 0,
  "TotalCount": 1
}
```





