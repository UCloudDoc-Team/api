# 动态绑定安全组 - AssociateSecGroupDynamic

## 简介

绑定安全组，动态调整绑定优先级

?> 备注：如果存在绑定配额已满的资源，则返回错误； 如果资源已绑定该安全组，则忽略该资源； 如果资源已使用最高优先级绑定其他安全组，则动态调整该资源已绑定的优先级（依次降低一个优先级），把接口中的安全组使用最高优先级绑定。

!> 以最高优先级绑定该安全组，如果最高优先级已使用，则动态调整优先级。 接口中如果需要调整优先级的资源比较多，接口会比较耗时，故限制批量资源数量为 20（超过这个数量会报错）。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AssociateSecGroupDynamic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AssociateSecGroupDynamic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId.N** | string | 资源短 ID 数组。支持数组模式。Type 为 string 数组。 |**Yes**|
| **SecGroupId** | string | 安全组ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AssociateSecGroupDynamic
&Region=cn-zj
&ProjectId=KmOqupAC
&ResourceId.N=OYfajOui
&SecGroupId=eqTlRyye
```

### 响应示例
    
```json
{
  "Action": "AssociateSecGroupDynamicResponse",
  "RetCode": 0
}
```





