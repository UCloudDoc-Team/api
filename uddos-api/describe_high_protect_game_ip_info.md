# 获取高防IP信息 - DescribeHighProtectGameIPInfo

## 简介

获取高防IP信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeHighProtectGameIPInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeHighProtectGameIPInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源短id |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0。 |No|
| **Limit** | int | 返回数据长度，默认为50。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 已经配置的总数 |No|
| **AvailableIPQuota** | int | 可用剩余ip配额数 |No|
| **GameIPInfo** | array[[*GameIpInfoTotal*](#GameIpInfoTotal)] | 高防IP信息 |No|

#### 数据模型


#### GameIpInfoTotal

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DefenceIP** | string | 高防IP |No|
| **LineType** | string | 线路类型 |No|
| **Cname** | string | 高防IP Cname |No|
| **RuleCnt** | int | 规则的个数 |No|
| **Status** | string | ip配置状态 |No|
| **SrcIP** | array[string] | 回源ip列表 |No|
| **Remark** | string | 用户mark |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeHighProtectGameIPInfo
&ResourceId="e4376373-e2c6-4062-84ab-c237667b4eb7 "
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeHighProtectGameIPInfoResponse",
  "AvailableIPQuota": 8,
  "GameIPInfo": [],
  "RetCode": 0,
  "TotalCount": 3
}
```





