# 获取加速域名原始日志 - GetUcdnDomainLog

## 简介

获取加速域名原始日志



!> 注解：日志数据最长保留三个月。

## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainLog)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DomainId.N** | string | 域名ID，创建加速域名时生成。默认全部域名 |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|
| **Type** | int | 查询粒度  0=default(没有粒度) 1=按小时  2=按天 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LogSet** | array[[*LogSetList*](#LogSetList)] | 获取日志的连接地址。具体参考下面LogSetList |No|

#### 数据模型


#### LogSetList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |No|
| **Logs** | array[[*LogSetInfo*](#LogSetInfo)] | 域名信息列表，参考LogSetInfo |No|

#### LogSetInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 日志时间UnixTime |No|
| **CnLog** | array[string] | 国内日志url列表 |No|
| **AbroadLog** | array[string] | 国外日志url列表 |No|

## 示例

### 请求示例
    
```
http://api.ucloud.cn/?Action=GetUcdnDomainLog
&ProjectId=xxxxx
&DomainId.0=ucdn-xxx
&BeginTime=1399132800
&EndTime=1399132800
```

### 响应示例
    
```json
{
  "Action": "GetUcdnDomainLogResponse",
  "LogSet": [
    {
      "Domain": "test_01.ucloud.cn",
      "Logs": [
        {
          "AbroadLog": [
            "http://test_01.ucloud.cn/test_abroad_01.log"
          ],
          "CnLog": [
            "http://test_01.ucloud.cn/test_cn_01.log"
          ],
          "Time": 1399132800
        }
      ]
    },
    {
      "Domain": "test_02.ucloud.cn",
      "Logs": [
        {
          "AbroadLog": [
            "http://test_02.ucloud.cn/test_abroad_01.log"
          ],
          "CnLog": [
            "http://test_02.ucloud.cn/test_cn_01.log"
          ],
          "Time": 1399132800
        }
      ]
    }
  ],
  "RetCode": 0
}
```





