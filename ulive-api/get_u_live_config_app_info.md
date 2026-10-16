# 获取域名以及其接入点列表 - GetULiveConfigAppInfo

## 简介

获取域名及接入点信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveConfigAppInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveConfigAppInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Domain.N** | string | 域名，如果不传该参数则获取用户帐号下所有直播域名配置信息,n为自然数多个域名 一次从0增加 |No|
| **DomainType** | string | 域名加速类型：publish(推流) play(播放)。默认推流 |No|
| **SubType** | string | 查询子类型(可扩展)，record(录制配置可用app) shift(时移可用app)，如果不传，则返回所有app |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ULiveConfigAppInfoData*](#ULiveConfigAppInfoData)] | 获取域名及接入点Data信息，参考ULiveConfigAppInfoData |**Yes**|

#### 数据模型


#### ULiveConfigAppInfoData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **AppNames** | array[string] | 接入点数组 |**Yes**|
| **Version** | string | 配置版本号 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveConfigAppInfo
&ProjectId=FHrdyAxn
&Domain.n=UTlFArhD
&DomainType=gOuBAnki
&SubType=FkkEvKCA
```

### 响应示例
    
```json
{
  "Action": "GetULiveConfigAppInfoResponse",
  "Data": "dsNcdZbj",
  "RetCode": 0
}
```





