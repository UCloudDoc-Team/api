# 修改资源自动续费标识 - ModifyAutoRenewFlag

## 简介

修改资源自动续费标识






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyAutoRenewFlag`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Flag** | string | 开关标识(TURN_ON: 打开; TURN_OFF: 关闭) |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Success** | int | 操作成功资源数量 |**Yes**|
| **Fail** | int | 操作失败资源数量 |**Yes**|
| **ResultSet** | array[[*ResultSet*](#ResultSet)] | 开关资源自动续费结果数组 |**Yes**|

#### 数据模型


#### ResultSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 续费结果(0:成功，失败返回错误码) |No|
| **Message** | string | 错误信息描述 |No|
| **ResourceId** | string | 资源ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyAutoRenewFlag
&ItemSet.n=PeQVqUMT
&Flag=asSCkphD
&ResourceId=GLxBNXXw
&RegionId=RGwvyHGR
&ResourceType=VCgvJpAf
```

### 响应示例
    
```json
{
  "Action": "ModifyAutoRenewFlagResponse",
  "Fail": 9,
  "ResultSet": [
    {
      "Message": "mxqrRAqq",
      "ResourceId": "rLHqlMdz",
      "RetCode": 4
    },
    {
      "Message": "cafLXQIW",
      "ResourceId": "iRVkrKje",
      "RetCode": 1
    },
    {
      "Message": "FVSkPkbj",
      "ResourceId": "yfhncBGh",
      "RetCode": 5
    }
  ],
  "RetCode": 0,
  "Success": 5
}
```





