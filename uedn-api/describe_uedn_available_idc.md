# 获取UEDN可用机房列表 - DescribeUEdnAvailableIDC

## 简介

获取UEDN可用机房列表








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEdnAvailableIDC`                        | **Yes** |
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
| **IdcList** | array[[*AvailableIdcInfo*](#AvailableIdcInfo)] | 机房列表 |No|

#### 数据模型


#### AvailableIdcInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IdcId** | string | 机房ID |No|
| **Name** | string | 机房名称 |No|
| **Isp** | string | 运营商 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **Type** | string | 运营商类型：0-其它, 1-一线城市单线,2-二线城市单线, 3-全国教育网, 4-全国三通 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEdnAvailableIDC
```

### 响应示例
    
```json
{
  "Action": "DescribeUEdnAvailableIDCResponse",
  "IdcList": [
    {
      "City": "fihuruud",
      "IdcId": "RbisyJSX",
      "Isp": "wxwbknxZ",
      "Name": "weOTWvdM",
      "Province": "hQibpslv",
      "Type": "HQawoRyh"
    }
  ],
  "RetCode": 0
}
```





