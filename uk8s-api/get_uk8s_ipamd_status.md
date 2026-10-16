# 获取ipamd插件的状态 - GetUK8SIpamdStatus

## 简介

查询 ipamd 插件的安装状态、版本、CNI 初始化模式及模式切换能力。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUK8SIpamdStatus`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID：在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，可选。 |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Installed** | boolean | 是否已经安装 |**Yes**|
| **Version** | string | 当前ipamd的版本 |**Yes**|
| **LastVersion** | string | ipamd可用最新版本 |**Yes**|
| **ReleaseDate** | int | 最新版本的发布日期 |**Yes**|
| **OpenTime** | int | 当前 ipamd 插件的创建时间，Unix 时间戳，单位秒。 |**Yes**|
| **CNIInitMode** | string | 当前 CNI 初始化模式。 |No|
| **CNIInitVersionReady** | boolean | 当前已安装的 ipamd 版本是否支持切换 CNI 初始化模式。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUK8SIpamdStatus
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tabEtpxk
&ClusterId=WDuPCzCV
```

### 响应示例
    
```json
{
  "Action": "GetUK8SIpamdStatusResponse",
  "Installed": false,
  "LastVersion": "EWDIRZbC",
  "OpenTime": 8,
  "ReleaseDate": 1,
  "RetCode": 0,
  "Version": "npORkzNo"
}
```





