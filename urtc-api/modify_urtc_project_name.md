# 修改项目名称 - ModifyURtcProjectName

## 简介

修改项目的基本信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyURtcProjectName`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 要修改的项目AppId |**Yes**|
| **AppName** | string | 修改后的新项目名称（不能为空） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AppId** | string | 修改的AppId |**Yes**|
| **AppName** | string | 修改后的名称 |**Yes**|
| **Msg** | string | RetCode返回0则为succed,若不为0则为具体的错误提示内容 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyURtcProjectName
&AppId=HcnYrWmv
&AppName=PuiNJbUw
```

### 响应示例
    
```json
{
  "Action": "ModifyURtcProjectNameResponse",
  "AppId": "zezMKcAL",
  "AppName": "lJbzNVWj",
  "Msg": "ZPoTUvOi",
  "RetCode": 0
}
```





