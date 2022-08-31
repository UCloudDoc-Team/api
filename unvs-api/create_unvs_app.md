# 创建应用 - CreateUNVSApp

## 简介

创建应用









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUNVSApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ApplicationName** | string | 应用名称 |**Yes**|
| **Platform** | int | 平台类型。1-Android 2-IOS 3-H5 |**Yes**|
| **BundleId** | string | IOS bundle id，当且仅当Platform为2时必填 |No|
| **PkgName** | string | android 包名，当且仅当Platform为1时必填 |No|
| **PkgSign** | string | android 包签名，当且仅当Platform为1时必填 |No|
| **Remark** | string | 备注 |No|
| **Businesses** | string | 绑定业务场景具体内容，若不为空，则表示创建应用、新增业务场景并绑定。该参数是json数组的base64编码结果。示例： 发送内容json数组（base64编码前）：[{"BusinessName":"BIZ-000","Purpose":1}] 。json数组中各参数的定义："BusinessName":业务场景名称，"Purpose":业务场景认证类型。其中必传参数为"BusinessName", "Purpose"。 实际调用本接口时Businesses传值（发送内容base64编码后）为：W3siQnVzaW5lc3NOYW1lIjoiQklaLTAwMCIsIlB1cnBvc2UiOjF9XQ== |No|
| **WebPageUrl** | string | h5 网页地址，当且仅当Platform为3时必填 |No|
| **OriginUrl** | string | h5 源地址，当且仅当Platform为3时必填 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 本次请求Uuid |**Yes**|
| **Data** | [*CreateUNVSAppResp*](#CreateUNVSAppResp) | null |**Yes**|

#### 数据模型


#### CreateUNVSAppResp

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ApplicationId** | string |  |No|
| **Platform** | int | 平台类型。1-Android 2-IOS 3-H5 |No|
| **BizItems** | array[[*AppBizItem*](#AppBizItem)] | 应用绑定的业务场景。 |No|

#### AppBizItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BusinessId** | string | 业务场景ID |No|
| **Name** | string | 业务场景名称 |No|
| **Purpose** | int | 业务场景认证类型。1-一键登录 2-号码检测 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUNVSApp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DUeYYImL
&BusinessName=KUijcSop
&Purpose=1
&Remark=OsQCVikP
&ApplicationId=fKIrmAzc
&BundleId=gzkdUWnF
&PkgName=rNprZTpG
&PkgSign=KNKSQVfu
&Businesses=rMKhRpIH
&WebPageUrl=yFOoLGGq
&OriginUrl=bgoPKEas
```

### 响应示例
    
```json
{
  "Action": "CreateUNVSAppResponse",
  "Data": {},
  "Message": "SJwrgwhk",
  "ReqUuid": "FFCVvtGb",
  "RetCode": 0
}
```





