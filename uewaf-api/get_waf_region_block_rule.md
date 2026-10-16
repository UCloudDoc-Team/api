# 查询区域IP封堵规则 - GetWafRegionBlockRule

## 简介

查询区域IP封堵记录









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetWafRegionBlockRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 查询域名  |**Yes**|
| **Offset** | int | 分页查询偏移设置 |**Yes**|
| **Limit** | int | 单页数量限制 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Count** | int | 规则数量 |No|
| **RuleList** | array[[*RegionBlackInfo*](#RegionBlackInfo)] | 规则列表，参考RegionBlackInfo |No|

#### 数据模型


#### RegionBlackInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | 规则ID |No|
| **Name** | string | 规则名称 |No|
| **FullDomain** | string | 所属域名 |No|
| **Action** | string | 执行动作 |No|
| **Regions** | string | 生效区域 |No|
| **Description** | string | 规则描述 |No|
| **TopOrganizationId** | int | 用户ID |No|
| **OrganizationId** | int | 项目ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "GetWafRegionBlockRuleResponse",
  "Count": 1,
  "RetCode": 0,
  "RuleList": [
    {
      "Action": "Deny",
      "Description": "全部",
      "FullDomain": "*.8cname.com",
      "ID": 1115,
      "Name": "1",
      "OrganizationId": 50148127,
      "Regions": "!CN",
      "TopOrganizationId": 50146955
    }
  ]
}
```





