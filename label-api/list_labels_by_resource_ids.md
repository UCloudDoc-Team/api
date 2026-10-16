# 根据资源ID获取标签列表 - ListLabelsByResourceIds

## 简介

根据资源ID获取标签列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListLabelsByResourceIds)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListLabelsByResourceIds`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceIds.N** | string | 资源id数组 |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为10，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 资源标签总数 |No|
| **Labels** | array[[*ListLabelsByResourceIdsLabel*](#ListLabelsByResourceIdsLabel)] | 资源标签数组 |No|

#### 数据模型


#### ListLabelsByResourceIdsLabel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id |**Yes**|
| **Key** | string | 标签键 |**Yes**|
| **Value** | string | 标签值 |**Yes**|
| **Category** | string | 标签类型，system：系统标签；custom：自定义标签 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListLabelsByResourceIds
&ResourceIds=pXUoXIsY
&Offset=1
&Limit=2
```

### 响应示例
    
```json
{
  "Action": "ListLabelsByResourceIdsResponse",
  "Labels": [
    {
      "Category": "txWdYOgd",
      "Key": "eXGXDGqx",
      "ResourceId": "ElPrCshS",
      "Value": "KDxqnFfY"
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





