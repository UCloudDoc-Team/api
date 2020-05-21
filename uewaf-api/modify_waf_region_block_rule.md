# 修改地域IP封堵规则 - ModifyWafRegionBlockRule

## 简介

修改地域IP封堵规则








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyWafRegionBlockRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要操作的域名 |**Yes**|
| **ID** | int | 规则ID |**Yes**|
| **Name** | string | 规则名称 |**Yes**|
| **ActionType** | string | 匹配Action，Accept or Deny（默认） |**Yes**|
| **BlockRegion** | string | 封堵地域编码，定义与添加的api相同 |**Yes**|
| **Description** | string | 备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=603
&ActionType=Deny
&BlockRegion=US
&Description=美国
```

### 响应示例
    
```json
{
  "Action": "ModifyWafRegionBlockRuleResponse",
  "RetCode": 0
}
```





