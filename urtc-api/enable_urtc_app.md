# 启用或者关停APP - EnableURtcApp

## 简介

启用或者关停指定的APP









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `EnableURtcApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 要关停的项目Appid |**Yes**|
| **AppEnable** | boolean | 是否启用App（true:启用，false:停用） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | 返回码不为0时具体的错误消息，为0时为succed |**Yes**|
| **Data** | [*EnableAppModel*](#EnableAppModel) | 改变状态成功时返回具体的appid和当前状态（参见EnableAppModel） |No|

#### 数据模型


#### EnableAppModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | appId |**Yes**|
| **AppStatue** | boolean | 项目状态 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=EnableURtcApp
&AppId=urtc-z4r1txxy
&AppEnable=false
```

### 响应示例
    
```json
{
  "Action": "EnableURtcAppResponse",
  "Data": {
    "AppId": "urtc-z4r1txxy",
    "AppStatue": false
  },
  "Msg": "Succed",
  "RetCode": 0
}
```





