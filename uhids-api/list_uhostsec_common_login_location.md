# 获取公共登录地列表 - ListUhostsecCommonLoginLocation

## 简介

获取公共登录地列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUhostsecCommonLoginLocation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Infos** | array[[*CommonLoginLocationInfo*](#CommonLoginLocationInfo)] | 公共登录地列表 |No|

#### 数据模型


#### CommonLoginLocationInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Country** | string | 国家 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **Account** | string | 账号 |No|
| **CreateTime** | string | 创建/修改时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUhostsecCommonLoginLocation
&ProjectId=BbdTEbry
```

### 响应示例
    
```json
{
  "Action": "ListUhostsecCommonLoginLocationResponse",
  "Infos": [
    {
      "City": "-",
      "Country": "中国",
      "Province": "香港"
    },
    {
      "City": "苏州",
      "Country": "中国",
      "Province": "江苏"
    },
    {
      "City": "-",
      "Country": "美国",
      "Province": "美国"
    },
    {
      "City": "广州",
      "Country": "中国",
      "Province": "广东"
    }
  ],
  "RetCode": 0
}
```





