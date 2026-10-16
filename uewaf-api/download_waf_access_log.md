# 下载访问日志 - DownloadWAFAccessLog

## 简介

下载访问日志









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DownloadWAFAccessLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要下载日志的域名 |**Yes**|
| **Date** | string | 日期，yyyy-mm-dd形式 |**Yes**|
| **LogType** | string | accessLog 访问日志，attackLog 攻击日志 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **URL** | array[string] | 文件下载的URL 列表，每小时提供一个文件 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DownloadWAFAccessLog
&ProjectId=org-xxx
&FullDomain=www.test.com
&LogType=attackLog
&Date=2020-04-03
```

### 响应示例
    
```json
{
  "Action": "DownloadWafAccessLogResponse",
  "RetCode": 0,
  "URL": [
    "http://uewaf.cn-bj.ufileos.com/*_8cname_com_20200403.accessLog.00.zip?Expires=1585985041\u0026Signature=CpiAddyTtFixYZynJ4KToFG3N3A%3D\u0026UCloudPublicKey=9uqRcyaNLuIhf1I4icUMsaiyB2HoWhs2zMaaGgYnV7dLb7m%2FsCP1JQ%3D%3D",
    "http://uewaf.cn-bj.ufileos.com/*_8cname_com_20200403.accessLog.14.zip?Expires=1585985041\u0026Signature=je3y7A%2Bjcs9eWKFvIE6k755pxcg%3D\u0026UCloudPublicKey=9uqRcyaNLuIhf1I4icUMsaiyB2HoWhs2zMaaGgYnV7dLb7m%2FsCP1JQ%3D%3D"
  ]
}
```





