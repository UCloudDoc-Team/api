# 获取直播加速域名配置 - GetLiveDomainConfigV2

## 简介

获取直播加速域名配置（新系统）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetLiveDomainConfigV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetLiveDomainConfigV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Domain.N** | string | 获取域名的配置信息，如果不传该参数则获取用户帐号下所有直播域名配置信息,n为自然数多个域名 一次从0增加 |No|
| **DomainType** | string | 域名加速类型：publish(推流) pull(拉流)不传获取所有类型的域名 <br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DomainList** | array[[*LiveDomainInfoV2*](#LiveDomainInfoV2)] | 域名信息列表 |**Yes**|

#### 数据模型


#### LiveDomainInfoV2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 域名资源ID |**Yes**|
| **AccessPoint** | string | 接入点 |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **Cname** | string | 该域名对应的CDN域名，客户CNAME到该域名推流或者播放 |**Yes**|
| **CreateTime** | int | 记录创建时间 |**Yes**|
| **DomainType** | string | 域名加速类型：publish(推流) pull(拉流) |**Yes**|
| **ResourceExtend** | string | 业务组 |**Yes**|
| **Status** | string | 加速状态。checking：配置中；enabled：加速中；failed：失败；deleting：删除中；disabling：禁用中；disabled：禁用 |**Yes**|
| **AuthConf** | [*AuthConf*](#AuthConf) | 鉴权配置 |**Yes**|
| **PublishNotifyConf** | [*PublishNotifyConf*](#PublishNotifyConf) | 推流回调配置 |**Yes**|
| **RecordConf** | [*RecordConf*](#RecordConf) | 录制配置 |**Yes**|
| **SourceInfo** | [*SourceInfo*](#SourceInfo) | 源站信息，DomainType=pull时才有 |No|

#### AuthConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AuthPublish** | string | 是否开启推流鉴权 on/off |No|
| **AuthPublishKey** | string | 鉴权key |No|
| **AuthPublishTimeout** | int | 超时时间 单位秒 |No|
| **AuthPlay** | string | 是否开启播放鉴权 on/off |No|
| **AuthPlayKey** | string | 鉴权key |No|
| **AuthPlayTimeout** | int | 超时时间 单位秒 |No|

#### PublishNotifyConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NotifyMethod** | string | 回调方法 get/post |No|
| **PublishNotify** | string | 推流开始回调 |No|
| **UnpublishNotify** | string | 推流结束回调 |No|
| **MetaNotify** | string | 媒体信息通知 |No|

#### RecordConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RecordSupport** | string | 是否支持录制 on/off |No|
| **RecordType** | string | 录制类型 hls,mp4,flv |No|
| **RecordForceRecord** | string | 是否强制录制 on/off |No|
| **RecordBucket** | string | 录制文件存放的bucket名称 |No|
| **RecordHostSuffix** | string | 录制文件存放的bucket主机后缀 |No|
| **RecordPublickKey** | string | 用户的公钥 |No|
| **RecordPrivateKey** | string | 用户的私钥 |No|
| **RecordCallback** | string | 录制回调地址 |No|

#### SourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SourcePlatformType** | string | 拉流加速时使用的源站平台，ucloud或者other<br />other表示自定义源站<br /> |No|
| **SourceList** | array[string] | 源站列表源站ip或者域名的数组(如果是域名则只有一个) |No|
| **SourceBackupList** | array[string] | 备份源站列表 |No|
| **PushDomainCname** | string | 当源站平台是ucloud时，表示该源站对应的推流域名的cname域名，自定义源站返回空 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetLiveDomainConfigV2
&ProjectId=VIuorikd
&Domain.n=HYYGluZo
&DomainType=EUNrJVTv
```

### 响应示例
    
```json
{
  "Action": "GetLiveDomainConfigV2Response",
  "DomainList": [
    {
      "AccessPoint": "ZeIeGHCH",
      "Cname": "mfjGujkT",
      "CreateTime": 1,
      "Domain": "lIgJLBTv",
      "DomainId": "prIqeBga",
      "DomainType": "QRubhcyh",
      "PushEndCallBackUrl": "MMfkzHCt",
      "PushStartCallBackUrl": "tqbxxRan",
      "ResourceExtend": "RLJFPyIe",
      "SourceInfo": {},
      "Status": "tjyrLVNo"
    }
  ],
  "RetCode": 0
}
```





