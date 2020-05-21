# 创建自动拦截策略接口 - AddAutoWafDomainBlackList

## 简介

当检测到攻击后，自动将访问源IP加入黑名单








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddAutoWafDomainBlackList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 防御的域名，只能选择已添加的域名 |**Yes**|
| **State** | string | 启用状态 Enable启用，否则禁用，默认启用 |No|
| **AttackType** | string | 攻击统计类型，默认全选；参数选项: protocol: 协议违规, xss: XSS攻击, sql: SQL注入, loopholes: 漏洞攻击, exec: 命令执行, webshell: WebShell上传, eaa: 越权访问, infoleak: 信息泄露, scan: 恶意扫描, cc: CC攻击, other: 其他 |No|
| **ActionType** | string | 检测到攻击后的动作， 默认为forbidden，支持captcha |No|
| **ExpireTime** | int | 添加黑名单的过期时间，单位分钟， 0 长期有效，默认60分钟 |No|
| **AttackCount** | int | 攻击阈值，默认10个 |No|
| **Interval** | int | 攻击统计区间，单位秒，默认60秒 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功返回的策略ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddAutoWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
&ActionType=forbidden
&State=Enable
&ExpireTime=60
&AttackCount=10
&Interval=60
```

### 响应示例
    
```json
{
  "Action": "AddAutoWafDomainBlackListResponse",
  "Id": 8,
  "RetCode": 0
}
```





