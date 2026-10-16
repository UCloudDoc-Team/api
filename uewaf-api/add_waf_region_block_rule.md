# 添加WAF区域IP封堵规则 - AddWafRegionBlockRule

## 简介

添加WAF区域IP封堵规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafRegionBlockRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 域名 |**Yes**|
| **Name** | string | 规则名称 |**Yes**|
| **BlockRegion** | string | 封堵地域编码，格式：国家代码:区域列表<br />大陆区支持省级和市级细分，其他只支持国家，e.g.:<br />CN:110000\|440300\|320000代表对北京市 深圳市 江苏省 的ip进行封堵; <br />US表示对美国ip进行封堵 |**Yes**|
| **ActionType** | string | 匹配Action，Accept or Deny（默认），Accept暂不支持 |**Yes**|
| **Description** | string | 备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功后返回的封堵规则ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&Name=test
&BlockRegion=CN
&ActionType=Deny
&Description=aaa
```

### 响应示例
    
```json
{
  "Action": "AddWafRegionBlockRuleResponse",
  "Id": 4,
  "RetCode": 0
}
```





