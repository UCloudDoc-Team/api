# 获取云手机Eip列表 - DescribeUPhoneEipList

## 简介

获取云手机Eip列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneEipList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Region** | string | Eip所属区域，没有该参数表示获取所有区域 |No|
| **Proportion** | string | 云手机与Eip绑定比例，没有该参数表示获取所有绑定比例 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **EipInfos** | array[[*EipInfo*](#EipInfo)] | Eip信息列表 |**Yes**|
| **TotalCount** | int | Eip信息数量 |No|

#### 数据模型


#### EipInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | Eip所属区域 |**Yes**|
| **EipId** | string | Eip资源ID |**Yes**|
| **EipIp** | string | Eip地址 |**Yes**|
| **Name** | string | Eip名称 |No|
| **Remark** | string | Eip备注 |No|
| **Proportion** | int | 云手机与Eip绑定比例 |No|
| **CreateTime** | int | 创建时间；格式为Unix时间戳 |No|
| **ExpireTime** | int | 到期时间；格式为Unix时间戳 |No|
| **ChargeType** | string | 计费模式。枚举值为： > 年 Year，按年付费； > Month，按月付费； > Dynamic，按小时预付费; 默认为月付 |No|
| **UPhoneIds** | array[string] | 绑定的云手机ID |No|
| **BindCount** | int | 当前绑定云手机数量 |No|
| **RemainCount** | int | 剩余可绑定手机数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneEipList
&ProjectId=DtWHuSxX
&Region=etXNejeV
&Proportion=xBXFRfyU
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneEipListResponse",
  "EipInfos": [
    {
      "ChargeType": "piTUkkLQ",
      "CreateTime": 3,
      "EipId": "kaxhxMeq",
      "EipIp": "qSwtLtoL",
      "ExpireTime": 6,
      "Name": "lpyUWHhd",
      "Proportion": 8,
      "Region": "fJPOKFql",
      "RemainCount": 4,
      "Remark": "tejHmcAk",
      "UPhoneIds": [
        "NIknnhkw"
      ]
    }
  ],
  "Message": "iFPibNtb",
  "RetCode": 0,
  "TotalCount": 7
}
```





