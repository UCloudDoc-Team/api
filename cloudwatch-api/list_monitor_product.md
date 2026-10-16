# 获取监控对象类型列表 - ListMonitorProduct

## 简介

获取监控对象类型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListMonitorProduct)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListMonitorProduct`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*ListMonitorProduct*](#ListMonitorProduct) | 返回数据 |**Yes**|
| **TraceId** | string | 链路ID |No|

#### 数据模型


#### ListMonitorProduct

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 查询结果总数 |No|
| **List** | array[[*Product*](#Product)] | 查询结果列表 |No|

#### Product

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | ID |No|
| **ProductType** | int | 资源类型ID |No|
| **ProductKey** | string | 资源类型唯一key |No|
| **ProductName** | string | 产品名称 |No|
| **ProductName1** | string | 产品子名称 |No|
| **ProductChName** | string | 产品中文名称 |No|
| **ProductEnName** | string | 产品英文名称 |No|
| **Metas** | string | {Type: 1\|2, Key:string, Name: string}[] -> JSON字符串 |No|
| **ProductGroup** | string | 产品分组 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListMonitorProduct
```

### 响应示例
    
```json
{
  "Action": "ListMonitorProductResponse",
  "Data": [
    {
      "Id": 3,
      "Metas": "CsFjPWNb",
      "ProductCNName": "VUsyDbNe",
      "ProductENName": "CXiVrIgN",
      "ProductGroup": "iDGbJEWE",
      "ProductKey": "ekrosCNG",
      "ProductName": "bpJOVIhD",
      "ProductName1": "NCFerAmk",
      "ProductType": 5
    }
  ],
  "Message": "gKJjAdES",
  "RetCode": 0,
  "TraceId": "SxNeegyN"
}
```





