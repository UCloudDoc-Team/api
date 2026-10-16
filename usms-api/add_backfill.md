# 添加回填 - AddBackfill

## 简介

用户通过接口发送消息，当消息在终端被消费，调用该接口，进行记录。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddBackfill)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddBackfill`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **SendNo** | string | 发送Number，记录一次发送请求的唯一性  |**Yes**|
| **Target** | string | 短信的接收目标,手机号需要添加国家码，比如(1)231xxxx  |**Yes**|
| **BackfillTime** | int | 回填时间，秒级别时间戳 |No|
| **Content** | string | 回填内容 |No|
| **SendTime** | int | 发送请求的时间，秒级别时间戳 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddBackfill
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=hXfXXHNM
&SendNo=RSwiTUiJ
&Target=YAOhCfLh
&BackfillTime=5
&Content=iXXgqdvC
&SendTime=7
```

### 响应示例
    
```json
{
  "Action": "AddBackfillResponse",
  "Message": "VOtOhTwd",
  "RetCode": 0
}
```





