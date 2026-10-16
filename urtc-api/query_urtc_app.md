# 查询app基本信息 - QueryURtcApp

## 简介

查询app基本信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 待查询app的appid(为空则是查询用户已创建的所有app或者不填此字段) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode返回0则为succed,若不为0则为具体的错误提示内容 |**Yes**|
| **Data** | array[[*AppModel*](#AppModel)] | 返回的app基本信息列表 |**Yes**|

#### 数据模型


#### AppModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | app名称 |**Yes**|
| **AppId** | string | appId |**Yes**|
| **AppStatue** | boolean | app状态(true:启用，false:停用) |**Yes**|
| **AppToken** | string | apptoken(接入rtc鉴权使用，妥善保管) |**Yes**|
| **AppCreatTime** | string | app创建时间 |**Yes**|
| **Id** | int | id序号 |**Yes**|
| **RecordStatue** | string | 录制是否开通(true:启用，false:停用) |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcApp
&AppId=fa3422b74ba211e9b10c00ff80725f6f
```

### 响应示例
    
暂无





