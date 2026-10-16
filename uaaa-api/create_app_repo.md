# 创建应用仓库加速实例 - CreateAppRepo

## 简介

创建应用仓库加速实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateAppRepo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateAppRepo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Name** | string | 名称 |**Yes**|
| **ChargeType** | string | 计费类型(年:'Year', 月:'Month',小时:'Dynamic') |**Yes**|
| **VPCId.N** | string | 待加速的VPCId ( 目前只允许一个) |**Yes**|
| **Description** | string | 应用仓库描述 |No|
| **Quantity** | int | 数量(ChargeType对应的数值): ChargeType = Month 时，默认0 ，其他条件为必须字段 |No|
| **RecordName.N** | string | 记录名称，需在给定列表中 |No|
| **CouponId** | string | 代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 应用仓库加速实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateAppRepo
&Region=cn-bj2
&ProjectId=org-XXX
&Name=YYCK01
&ChargeType=Month
&VPCId.n=uvnet-XXXX
&Description=YYCK-DESC
&Quantity=1
&RecordName.0=*.xyz.com
&CouponId=KAxnpXFB
```

### 响应示例
    
```json
{
  "Action": "CreateAppRepoResponse",
  "InstanceId": "uaaa-XXXXX",
  "Message": "DLXSOhln",
  "RetCode": 0
}
```





