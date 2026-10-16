# 查询IP信息 - QueryIpLocation

## 简介

查询IP信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryIpLocation)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryIpLocation`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip.N** | string | ip列表 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*IpLocationInfo*](#IpLocationInfo)] | IP信息列表 |**Yes**|

#### 数据模型


#### IpLocationInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | 客户端请求的ip |No|
| **Area** | string | 地区 |No|
| **Isp** | string | 运营商 |No|
| **City** | string | 城市 |No|
| **Exist** | boolean | ip是否存在 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryIpLocation
&Ip.n=JjOUYgbl
```

### 响应示例
    
```json
{
  "Action": "QueryIpLocationResponse",
  "Data": [
    {
      "Area": "mVVetvPX",
      "City": "qGLzrhND",
      "Exist": false,
      "Ip": "JNvcgwzh",
      "Isp": "NbVGrLKP"
    }
  ],
  "RetCode": 0
}
```





