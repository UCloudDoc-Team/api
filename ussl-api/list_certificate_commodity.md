# 查询产品列表 - ListCertificateCommodity

## 简介

查询产品列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCertificateCommodity`                        | **Yes** |
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
| **Recommended** | array[[*CertificateCommodity*](#CertificateCommodity)] | 推荐的产品 |**Yes**|
| **All** | array[[*CertificateCommodity*](#CertificateCommodity)] | 所有产品 |**Yes**|

#### 数据模型


#### CertificateCommodity

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | ID |No|
| **CertificateName** | string | 名称 |No|
| **CertificateBrand** | string | 品牌 |No|
| **CertificateCat** | string | 分类 |No|
| **ProductID** | int | 产品ID |No|
| **DomainMaxLimit** | int | 最大购买数量 |No|
| **DomainMinLimit** | int | 最小购买数量 |No|
| **Channel** | string | ca渠道 |No|
| **CertificateCnName** | string | 证书名 |No|
| **CSRAlgorithms** | array[[*CSRAlgorithmInfo*](#CSRAlgorithmInfo)] | 算法 |No|

#### CSRAlgorithmInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Algorithm** | string | 算法。<br /><br />支持RSA, ECDSA, SM2 三种值 |No|
| **AlgorithmOption** | array[string] | 算法key的长度 。 <br />1. RSA支持2048,3072,4096<br />2. ECDSA支持p256,p384,p512<br />3. SM2支持 p256 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCertificateCommodity
&Channel=1
```

### 响应示例
    
```json
{
  "Action": "ListCertificateCommodityResponse",
  "All": [
    {
      "Brand": "",
      "TypeSet": [
        {
          "CommoditySet": {
            "CSRAlgorithms": "",
            "CertificateBrand": "",
            "CertificateCat": "",
            "CertificateCnName": "",
            "CertificateName": "",
            "Channel": "",
            "DomainMaxLimit": "",
            "DomainMinLimit": "",
            "ID": "",
            "ProductID": ""
          },
          "Type": ""
        }
      ]
    }
  ],
  "Recommended": [
    {
      "Brand": "",
      "TypeSet": [
        {
          "CommoditySet": {
            "CSRAlgorithms": "",
            "CertificateBrand": "",
            "CertificateCat": "",
            "CertificateCnName": "",
            "CertificateName": "",
            "Channel": "",
            "DomainMaxLimit": "",
            "DomainMinLimit": "",
            "ID": "",
            "ProductID": ""
          },
          "Type": ""
        }
      ]
    }
  ],
  "RetCode": 0
}
```





