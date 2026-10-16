# 获取USMC迁移计划 - ListUSMCPlan

## 简介

获取USMC迁移计划









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUSMCPlan`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ListPlanItem*](#ListPlanItem)] | []ListPlanItem |**Yes**|

#### 数据模型


#### ListPlanItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PlanId** | string | 迁移计划ID |No|
| **Name** | string | 名称 |No|
| **SourceVendor** | string | 迁移源 |No|
| **SourceRegion** | string | 迁移来源地域 |No|
| **TargetRegion** | string | 迁移目标地域 |No|
| **NetworkType** | int | 网络类型， 10:外网, 20: 内网, 30:专线 |No|
| **AgentDownloadUrl** | string | 客户端下载地址 |No|
| **CreateTime** | int | 创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUSMCPlan
&PlanId=NTbVurgb
&Offset=LAXVrJkb
&Limit=pdkNUQvA
```

### 响应示例
    
```json
{
  "Action": "ListUSMCPlanResponse",
  "Data": [
    {
      "AgentDownloadUrl": "jSdNWvqa",
      "CreateTime": 4,
      "Id": "QhPxRTiO",
      "Name": "dKcNkBwb",
      "NetWorkType": 2,
      "Source": "PnAACDVz",
      "SourceRegion": "XFajGCiY",
      "TargetRegion": "lvrBfwZI"
    }
  ],
  "Message": "SdLiVRxr",
  "RetCode": 0
}
```





