# 接口获取鉴权信息(非标使用) - GetAuthConfig

## 简介

接口获取鉴权信息（非标使用）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAuthConfig)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAuthConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Domain** | string | 希望获取的域名，不传则获取所有 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AuthConfigs** | array[[*KwaiDomainAuthConfig*](#KwaiDomainAuthConfig)] | 鉴权配置列表 |No|

#### 数据模型


#### KwaiDomainAuthConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |**Yes**|
| **Config** | array[[*KwaiAuthConfig*](#KwaiAuthConfig)] |  |**Yes**|

#### KwaiAuthConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 类型  pkey / ksc / typeA |**Yes**|
| **Keys** | array[[*KwaiAuthKv*](#KwaiAuthKv)] |  |No|

#### KwaiAuthKv

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | key信息 |**Yes**|
| **Iv** | string | iv信息 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAuthConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DFzPRVqI
&Domain=HhTjSARl
```

### 响应示例
    
```json
{
  "Action": "GetAuthConfigResponse",
  "AuthConfigs": [
    {
      "Config": [
        {
          "Keys": [
            {
              "Iv": "222",
              "Key": "111"
            }
          ],
          "Type": "pkey"
        },
        {
          "Keys": [
            {
              "Iv": "444",
              "Key": "333"
            },
            {
              "Iv": "666",
              "Key": "555"
            }
          ],
          "Type": "ksc"
        }
      ],
      "Domain": "www.xx.com"
    }
  ],
  "RetCode": 0
}
```





