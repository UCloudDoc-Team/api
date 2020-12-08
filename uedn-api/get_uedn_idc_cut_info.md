# 获得机房割接信息 - GetUEdnIDCCutInfo

## 简介

获取机房割接信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEdnIDCCutInfo`                        | **Yes** |
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
| **IDCCutInfo** | array[[*IDCCutInfo*](#IDCCutInfo)] | 机房割接信息 |**Yes**|
| **TotalCount** | int | 满足条件的机房总数 |No|

#### 数据模型


#### IDCCutInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IDCName** | string | 机房名称 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **StartTime** | int | 割接开始时间 |No|
| **EndTime** | int | 割接结束时间 |No|
| **CutType** | string | 割接类型（中断、抖动、断电） |No|
| **ResourceSet** | array[[*ResourceSet*](#ResourceSet)] | 受影响的资源信息列表 |No|

#### ResourceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeId** | string | 节点id |No|
| **OuterIps** | array[string] | 机器外网ip集合 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEdnIDCCutInfo
```

### 响应示例
    
```json
{
  "Action": "GetUEdnIDCCutInfoResponse",
  "IDCCutInfo": [
    {
      "City": "bbJBZCTX",
      "CutType": "IbUDCrWO",
      "EndTime": 9,
      "IDCName": "baXTsuGb",
      "Province": "XyLfwepV",
      "ResourceSet": [
        {
          "NodeId": "aqkDpRSA",
          "OuterIps": [
            "cZEgqCsO"
          ]
        }
      ],
      "StartTime": 2
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





