# 获取角色列表 - DescribeCharacterList

## 简介

获取角色列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCharacterList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCharacterList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Offset** | int | 角色列表的偏移量，默认为0 |No|
| **Limit** | int | 角色列表的最大数量，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CharacterSet** | array[[*CharacterSet*](#CharacterSet)] | JSON格式的角色列表实例，每项参数参见下面的 ResponseItem |**Yes**|
| **TotalCount** | int | 角色总数 |**Yes**|

#### 数据模型


#### CharacterSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CharacterId** | string | 角色ID |**Yes**|
| **CharacterName** | string | 角色名 |**Yes**|
| **CharacterDescription** | string | 角色描述 |**Yes**|
| **Modifiable** | boolean | 可修改性 |**Yes**|
| **PermissionSet** | array[[*PermissionSet*](#PermissionSet)] | 权限列表 |**Yes**|

#### PermissionSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Add** | array[string] | 有增权限的产品列表 |**Yes**|
| **Del** | array[string] | 有删权限的产品列表 |**Yes**|
| **Mod** | array[string] | 有改权限的产品列表 |**Yes**|
| **Get** | array[string] | 有查权限的产品列表 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCharacterList
&Offset=0
&Limit=7
```

### 响应示例
    
```json
{
  "Action": "DescribeCharacterListResponse",
  "CharacterSet": [
    {
      "CharacterDescription": "管理员",
      "CharacterId": "Admin",
      "CharacterName": "Admin",
      "Modifiable": false,
      "PermissionSet": {
        "Add": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST",
          "ULB",
          "UMARKET",
          "UMEM",
          "UNET",
          "USEC",
          "UVIDEO",
          "UHADOOP",
          "UKAFKA",
          "UDW",
          "UDSET",
          "UAI",
          "UAI-TRAINING",
          "ULIVE",
          "UDOCKER",
          "UHUB",
          "UWAF",
          "UDDB",
          "UHIDS",
          "DBAUDIT",
          "UK8S",
          "PATHX",
          "UKMS",
          "UES",
          "UFLINK"
        ],
        "Del": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST",
          "ULB",
          "UMARKET",
          "UMEM",
          "UNET",
          "USEC",
          "UVIDEO",
          "UHADOOP",
          "UKAFKA",
          "UDW",
          "UDSET",
          "UAI",
          "UAI-TRAINING",
          "ULIVE",
          "UDOCKER",
          "UHUB",
          "UWAF",
          "UDDB",
          "UHIDS",
          "DBAUDIT",
          "UK8S",
          "PATHX",
          "UKMS",
          "UES",
          "UFLINK"
        ],
        "Get": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST",
          "ULB",
          "UMARKET",
          "UMEM",
          "UNET",
          "USEC",
          "UVIDEO",
          "UHADOOP",
          "UKAFKA",
          "UDW",
          "UDSET",
          "UAI",
          "UAI-TRAINING",
          "ULIVE",
          "UDOCKER",
          "UHUB",
          "UWAF",
          "UDDB",
          "UHIDS",
          "DBAUDIT",
          "UK8S",
          "PATHX",
          "UKMS",
          "UES",
          "UFLINK"
        ],
        "Mod": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST",
          "ULB",
          "UMARKET",
          "UMEM",
          "UNET",
          "USEC",
          "UVIDEO",
          "UHADOOP",
          "UKAFKA",
          "UDW",
          "UDSET",
          "UAI",
          "UAI-TRAINING",
          "ULIVE",
          "UDOCKER",
          "UHUB",
          "UWAF",
          "UDDB",
          "UHIDS",
          "DBAUDIT",
          "UK8S",
          "PATHX",
          "UKMS",
          "UES",
          "UFLINK"
        ]
      }
    },
    {
      "CharacterDescription": "",
      "CharacterId": "lptabl",
      "CharacterName": "test",
      "Modifiable": true,
      "PermissionSet": {
        "Add": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST"
        ],
        "Del": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST"
        ],
        "Get": [
          "HYBRID",
          "PHOST",
          "UCDN",
          "UDB",
          "UDDP",
          "UDISK",
          "UFILE",
          "UHOST"
        ],
        "Mod": null
      }
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





