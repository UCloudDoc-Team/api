# 路由策略增、删、改 - ModifyRouteRule

## 简介

路由策略增、删、改






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyRouteRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyRouteRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **RouteTableId** | string | 通过DescribeRouteTable拿到 |**Yes**|
| **RouteRule.N** | string | 格式: RouteRuleId \| 目的网段 \| 下一跳类型（支持INSTANCE、VIP） \| 下一跳 \|优先级（保留字段，填写0即可）\| 备注 \| 增、删、改标志（add/delete/update） 。"添加"示例: test_id \| 10.8.0.0/16 \| instance \| uhost-xd8ja \| 0 \| Default Route Rule\| add (添加的RouteRuleId填任意非空字符串) 。"删除"示例: routerule-xk3jxa \| 10.8.0.0/16 \| instance \| uhost-xd8ja \| 0 \| Default Route Rule\| delete (RouteRuleId来自DescribeRouteTable中)     <br />。“修改”示例: routerule-xk3jxa \| 10.8.0.0/16 \| instance \| uhost-cjksa2 \| 0 \| Default Route Rule\| update (RouteRuleId来自DescribeRouteTable中)    |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyRouteRule
&Region=qdFTcuIX
&ProjectId=ivrBxzEB
&RouteTableId=LjMBHdyz
&RouteRule.n=PXrUoFBk
```

### 响应示例
    
```json
{
  "Action": "ModifyRouteRuleResponse",
  "RetCode": 0
}
```





