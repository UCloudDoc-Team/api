# 添加webrisk白名单 - AddUHostSecWebRiskWhiteRule

## 简介

添加webrisk白名单









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUHostSecWebRiskWhiteRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Data** | string | webrisk白名单规则信息（值为以下字段的json转base64后字符串，json格式：{"Data":[{"IP":{"Type":"subnet","IPs":["192.168.1.0/24","172.36.1.0-172.36.255.255"]},"Type":"不安全的配置","RuleId":"30001","RiskDesc":"未删除的.git目录","Detail":"未删除的.git目录，黑客可以直接下载git相关文件","FileName":"/var/www/html/DiscuzX/install/index.php"},{"IP":{"Type":"all","IPs":[]},"Type":"不安全的配置","RuleId":"30001","RiskDesc":"未删除的.git目录","Detail":"未删除的.git目录，黑客可以直接下载git相关文件","FileName":"/var/www/html/DiscuzX/install/index.php"}]}） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Success** | int | 成功数 |No|
| **Fail** | int | 失败数 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUHostSecWebRiskWhiteRule
&ProjectId=mMdZfJpC
&Data=pJOCxQgR
```

### 响应示例
    
```json
{
  "Action": "AddUHostSecWebRiskWhiteRuleResponse",
  "Fail": 3,
  "RetCode": 0,
  "Success": 6
}
```





