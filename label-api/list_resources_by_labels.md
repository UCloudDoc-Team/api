# 根据标签获取资源列表 - ListResourcesByLabels

## 简介

根据标签获取资源列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListResourcesByLabels)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListResourcesByLabels`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Labels.N.Key** | string | 标签键 |**Yes**|
| **Labels.N.Value** | string | 标签值 |**Yes**|
| **ResourceTypes.N** | string | 资源类型数组 |**Yes**|
| **ProjectIds.N** | string | 项目id数组 |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为 0，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 资源总数 |No|
| **Resources** | array[[*ListResourcesByLabelsResource*](#ListResourcesByLabelsResource)] | 资源列表 |No|

#### 数据模型


#### ListResourcesByLabelsResource

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目id |**Yes**|
| **ResourceId** | string | 资源id |**Yes**|
| **ResourceName** | string | 资源名称 |**Yes**|
| **ProjectName** | string | 项目名称 |**Yes**|
| **ResourceType** | string | 资源类型 |**Yes**|
| **Labels** | array[[*ListResourcesByLabelsLabel*](#ListResourcesByLabelsLabel)] | 标签数组 |**Yes**|

#### ListResourcesByLabelsLabel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 标签键 |No|
| **Value** | string | 标签值 |No|
| **Category** | string | 标签类型，system：系统标签；custom：自定义标签 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListResourcesByLabels
&Labels=ntCdGAyy
&Offset=2
&Limit=3
&Labels.N.Value=YXDLevRF
&ResourceTypes.N=UuUvHKWO
&ProjectIds.N=XgLtzEFf
```

### 响应示例
    
```json
{
  "Action": "ListResourcesByLabelsResponse",
  "Resources": [
    {
      "Labels": [
        {
          "Category": "lKEsvGZE",
          "Key": "ZIUFsoXl",
          "Value": "JWILJdgN"
        }
      ],
      "ProjectId": "ndAdjmsF",
      "ProjectName": "aNXZWXmR",
      "Region": "fsAJwsSj",
      "ResourceId": "NAVCNQVl",
      "ResourceName": "zQRrbpKU",
      "ResourceType": "iWNdsqXo",
      "Zone": "NcjklQqz"
    }
  ],
  "RetCode": 0,
  "TotalCount": 8
}
```





