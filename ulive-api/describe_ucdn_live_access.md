# 获取直播加速 --- 【需要下线】 - DescribeUcdnLiveAccess

## 简介

获取直播加速 -- 【需要下线】

?> 待下线




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUcdnLiveAccess)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUcdnLiveAccess`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 创建直播加速生成的Id，默认获取帐号下所有直播加速 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的直播加速个数 |No|
| **ChargeType** | string | 表示当前的计费方式，traffic代表按流量包计费 bandwidth按带宽付费 |No|
| **LastChargeType** | string | 表示最后一次切换的计费方式，traffic代表按流 量包计费，bandwidth按带宽付费 |No|
| **DomainSet** | array[[*UcdnLiveAccessDomainSet*](#UcdnLiveAccessDomainSet)] | 获取的域名信息，具体参考下面 UcdnLiveAccessDomainSet |No|

#### 数据模型


#### UcdnLiveAccessDomainSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

## 示例

### 请求示例
    
```
http://api.spark.ucloud.cn/?Action=DescribeUcdnLiveAccess
```

### 响应示例
    
```json
{
  "Action": "DescribeUcdnLiveAccessResponse",
  "DomainSet": [
    {
      "AccessPoint": "live",
      "CreateTime": 1398780360,
      "DomainId": "domain-0331qd",
      "PublishCname": "e43b342b.cdn.ucloud.com.cn",
      "PublishDomain": "publish.ucloud.com.cn",
      "RtmpPlayCname": "efa7bf.cdn.ucloud.com.cn",
      "RtmpPlayDomain": "rtmp.ucloud.com.cn",
      "Status": "configuring"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





