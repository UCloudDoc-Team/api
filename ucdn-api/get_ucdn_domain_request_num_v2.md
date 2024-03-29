# 【待下线】获取域名请求数 - GetUcdnDomainRequestNumV2

## 简介

获取域名请求数

?> 该接口即将下线，获取域名请求数可使用最新接口GetUcdnDomainRequestNumV3 




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainRequestNumV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainRequestNumV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | int | 时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天的粒度, 3=按1分钟） |**Yes**|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp |**Yes**|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Areacode** | string | 查询区域 cn代表国内 abroad代表海外，只支持国内 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RequestList** | array[[*RequestInfo*](#RequestInfo)] | 请求数实例表。 |No|

#### 数据模型


#### RequestInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **CdnRequest** | float | 返回值返回指定时间区间内的cdn收到的请求次数之和 |No|
| **OriginRequest** | float | 返回值返回指定时间区间内的cdn回源的请求次数之和 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnDomainRequestNumV2
&ProjectId=TGTBMbzo
&Type=1
&DomainId.n=mTbgqcTn
&Areacode=nAPpQFkD
&BeginTime=2
&EndTime=9
```

### 响应示例
    
```json
{
  "Action": "GetUcdnDomainRequestNumV2Response",
  "RequestList": [
    {
      "CdnRequest": 6,
      "OriginRequest": 7,
      "Time": 4
    }
  ],
  "RetCode": 0
}
```





