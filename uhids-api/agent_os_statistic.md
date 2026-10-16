# 主机操作系统分布 - AgentOSStatistic

## 简介

统计当前主机安装哪些系统，并统计各系统安装数









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AgentOSStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*OSList*](#OSList) | 操作系统安装量统计结果 |**Yes**|

#### 数据模型


#### OSList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 主机操作系统总数 |No|
| **OS** | array[[*OSInfo*](#OSInfo)] | 主机操作系统列表 |No|

#### OSInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 主机数 |No|
| **OSType** | string | 系统类型 |No|
| **Version** | array[[*OSVersion*](#OSVersion)] | 系统版本列表 |No|

#### OSVersion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 系统名称 |No|
| **Count** | int | 该版本系统安装主机数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AgentOSStatistic
&ProjectId=bBsnqfGx
&TopN=1
```

### 响应示例
    
```json
{
  "Action": "AgentOSStatisticResponse",
  "Result": {},
  "RetCode": 0
}
```





