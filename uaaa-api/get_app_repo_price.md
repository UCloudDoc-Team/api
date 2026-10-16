# 获取应用仓库实例价格 - GetAppRepoPrice

## 简介

获取应用仓库实例价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAppRepoPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAppRepoPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ChargeType** | string | 计费类型 |**Yes**|
| **Quantity** | int | 数量（和ChargeType相关）: ChargeType = Month， 默认值为0 ， 其他情况为必传字段 |No|
| **DomainQuantity** | int | 域名绑定数量( >= 0) ,默认: 0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAppRepoPrice
&Region=cn-bj2
&ProjectId=org-XXXX
&ChargeType=Dynamic
&Quantity=1
&DomainQuantity=5
```

### 响应示例
    
```json
{
  "Action": "GetAppRepoPriceResponse",
  "Price": 4.77113,
  "RetCode": 0
}
```





