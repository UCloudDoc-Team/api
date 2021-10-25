# 获取全球接入源站可选列表 - DescribeUGA3Area

## 简介

获取全球接入源站可选列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUGA3Area)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGA3Area`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **IPList** | string | IP集合，非必填。如果填IP或者域名，会推荐一个地域在返回列表的第一个，源站IP集合，以逗号分隔[127.0.0.1,127.0.0.2] |No|
| **Domain** | string | 域名，非必填。如果填IP或者域名，会推荐一个地域在返回列表的第一个 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AreaSet** | array[[*ForwardArea*](#ForwardArea)] | 支持源站的地区,比如：<br />AreaSet[{<br />            "Area": "首尔",<br />            "AreaCode": "ICN",<br />            "CountryCode": "CN",<br />            "ContinentCode": "CN"<br />        }]<br /><br />ContinentCode:["CN","NA","OT"];"CN":表示国内，"NA":表示美洲，“OT"：表示欧洲等其他地区 |No|

#### 数据模型


#### ForwardArea

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaCode** | string | 源站区域代码 |**Yes**|
| **Area** | string | 源站区域中文 |**Yes**|
| **CountryCode** | string | 国家代码 |**Yes**|
| **FlagUnicode** | string | 国旗unicode |**Yes**|
| **FlagEmoji** | string | 国旗 emoji |**Yes**|
| **ContinentCode** | string | 大陆代码 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGA3Area
&ProjectId=JsYrEICS
&IPList=ydErVUdq
&Domain=GlVddTda
```

### 响应示例
    
```json
{
  "Action": "DescribeUGA3AreaResponse",
  "AreaSet": [
    {
      "AreaSet": [
        "mRuBruDW"
      ]
    }
  ],
  "Message": "upQNMjPD",
  "RetCode": 0
}
```





