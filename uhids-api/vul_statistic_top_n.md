# 高危漏洞TOP N - VulStatisticTopN

## 简介

某种类型漏洞存在主机的主机数TOP N









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `VulStatisticTopN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **TopN** | int | 感染主机数量最多的前N个漏洞，最小为10 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | array[[*VulStatisticTopNInfo*](#VulStatisticTopNInfo)] | 感染主机数量最多的前N个漏洞列表信息 |**Yes**|

#### 数据模型


#### VulStatisticTopNInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VulID** | string | 漏洞ID |**Yes**|
| **Name** | string | 漏洞名称 |**Yes**|
| **AgentCount** | int | 存在该漏洞的主机数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=VulStatisticTopN
&ProjectId=drlAkuki
&TopN=5
```

### 响应示例
    
```json
{
  "Action": "VulStatisticTopNResponse",
  "Result": [
    {
      "AgentCount": 9,
      "Name": "PuWrejdm",
      "VulID": "DqGjSPJw"
    }
  ],
  "RetCode": 0
}
```





