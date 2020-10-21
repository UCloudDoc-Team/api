# 按省份运营商获取域名请求数【新】 - GetUcdnProIspRequestNumV2

## 简介

按省份运营商获取域名请求数






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnProIspRequestNumV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnProIspRequestNumV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 查询的起始日期，格式为Unix Timestamp  忽略时间部分 |**Yes**|
| **EndTime** | int | 查询的结束日期，格式为Unix Timestamp  忽略时间部分 |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Province.N** | string | 省份代码，可以传多个，不传则查询所有省份 |No|
| **Isp** | string | 运营商代码，一次只能查询一个运营商，不传递默认取所有运营商 |No|
| **Type** | int | 时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天粒度，3表示按照一分钟粒度） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RequestNumSet** | array[[*ProIspRequestNumSetV2*](#ProIspRequestNumSetV2)] | 按省份的请求数实例表。具体参考下面RequestList |**Yes**|

#### 数据模型


#### ProIspRequestNumSetV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Province** | string | 省份代码 |**Yes**|
| **RequestList** | array[[*ProIspRequestListV2*](#ProIspRequestListV2)] | 省份请求数实例表 ProIspRequestListV2 |**Yes**|

#### ProIspRequestListV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 带宽获取的时间点。格式：时间戳 |No|
| **CdnRequest** | float | 返回值返回指定时间区间内的请求数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUcdnProIspRequestNumV2
&ProjectId=sbEAKCLS
&BeginTime=6
&EndTime=2
&DomainId.n=ruTjptSq
&Province.n=fdFLRcCa
&Isp=rYesZQIs
&Type=2
```

### 响应示例
    
```json
{
  "Action": "GetUcdnProIspRequestNumV2Response",
  "RequestNumSet": [
    {
      "Province": "QzrNPuTX",
      "RequestList": [
        {
          "RequestNum": 4.99469,
          "Time": 5
        }
      ]
    }
  ],
  "RetCode": 0
}
```





