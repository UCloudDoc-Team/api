# 修改自动拦截规则 - ModifyAutoWafDomainBlackList

## 简介

修改自动拦截规则，当检测到攻击后，自动将访问源IP加入黑名单









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyAutoWafDomainBlackList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ID** | int | 需要修改的自动拦截规则ID |**Yes**|
| **FullDomain** | string | 防御的域名，只能选择已添加的域名 |**Yes**|
| **AttackType** | string | 攻击种类，默认统计所有攻击种类，可选值：all\|protocol\|xss\|sql\|loopholes\|exec\|webshell\|eaa\|infoleak\|scan\|cc\|other等 |No|
| **State** | string | 枚举值："Enable", "Disable"，控制规则是否生效 |No|
| **ActionType** | string | 检测到攻击后的动作， 默认为forbidden，支持captcha |No|
| **ExpireTime** | int | 规则生效后， 添加黑名单的过期时间，单位分钟， 0 长期有效，默认60分钟 |No|
| **AttackCount** | int | 攻击阈值，默认10个 |No|
| **Interval** | int | 攻击统计区间，单位秒，默认60秒 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyAutoWafDomainBlackList
&ProjectId=org-xxx
&ID=2
&FullDomain=www.test.com
&ActionType=forbidden
&ExpireTime=60
&AttackCount=10
&AttackType=eaa
&Interval=60
```

### 响应示例
    
```json
{
  "Action": "ModifyAutoWafDomainBlackListResponse",
  "RetCode": 0
}
```





