# 创建苹果审核加速通道 - CreateCommonUGAInstance

## 简介

创建苹果审核加速通道






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCommonUGAInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCommonUGAInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Quantity** | int | 购买周期 |**Yes**|
| **ChargeType** | string | 计费模式 |**Yes**|
| **UGAType** | string | AppStore: 苹果审核加速 |**Yes**|
| **Name** | string | 加速实例名称 |**Yes**|
| **IPList** | string | 加速源IP，多个IP用逗号隔开(,)隔开;IPList和Domain二选一必填 |No|
| **Domain** | string | 加速源域名;IPList和Domain二选一必填 |No|
| **TCP.N** | string | TCP端口号，端口必填，AppStore可以同时加多个TCP和UDP端口，如TCP.0，TCP.1，UDP.0等 |No|
| **UDP.N** | string | UDP端口号，端口必填，AppStore可以同时加多个TCP和UDP端口，如TCP.0，TCP.1，UDP.0等 |No|
| **CouponId** | string | 代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGAId** | string | 全球加速ID |**Yes**|
| **CName** | string | 全球加速cname |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCommonUGAInstance
&Name=HpfvLVnf
&IPList=LwaCqchO
&Domain=lhWOaZpu
&TaskSet=KJEUbcel
&ChargeType=Year
&Quantity=wyeuyaQP
&CouponId=TAhWCFHn
```

### 响应示例
    
```json
{
  "Action": "CreateCommonUGAInstanceResponse",
  "CName": "cbRwxdoI",
  "RetCode": 0,
  "UGAAId": "hFfpzNWL"
}
```





