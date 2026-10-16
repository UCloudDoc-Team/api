# 查询主机安全周报 - QueryWeekReportList

## 简介

查询主机安全周报









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryWeekReportList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **PageSize** | int | 页大小 |No|
| **PageIndex** | int | 第N页 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | array[[*WeekReport*](#WeekReport)] | 文件列表 |**Yes**|
| **Total** | int | 记录总数 |No|

#### 数据模型


#### WeekReport

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FileName** | string | 文件名称 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryWeekReportList
&ProjectId=dylqflLq
&PageSize=1
&PageIndex=6
```

### 响应示例
    
```json
{
  "Action": "QueryWeekReportListResponse",
  "Result": [
    "QVxnHddY"
  ],
  "RetCode": 0,
  "Total": 9
}
```





