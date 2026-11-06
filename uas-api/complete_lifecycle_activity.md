# 完成生命周期挂钩活动 - CompleteLifecycleActivity

## 简介

完成生命周期挂钩活动






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CompleteLifecycleActivity`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表 |**Yes**|
| **LifecycleHookId** | string | 生命周期挂钩 Id |**Yes**|
| **LifecycleActivityId** | string | 生命周期挂钩活动 Id |**Yes**|
| **LifecycleHookPolicy** | string | 实例挂起状态结束后执行的策略，如不填则表示遵循所属生命周期挂钩的策略。取值：CONTINUE：继续执行；ABANDON：中止后续操作 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LifecycleActivityId** | string | 生命周期挂钩活动 Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CompleteLifecycleActivity
&Region=cn-zj
&LifecycleHookId=NrqWOdkw
&LifecycleActivityId=SLxAHoqI
&LifecycleHookPolicy=NzPXylFS
```

### 响应示例
    
```json
{
  "Action": "CompleteLifecycleActivityResponse",
  "LifecycleActivityId": "vzUmPzVI",
  "RetCode": 0
}
```





