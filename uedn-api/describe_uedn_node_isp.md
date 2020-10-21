# 获取机房信息 - DescribeUEdnNodeISP

## 简介

获取物理机房信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEdnNodeISP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IspName** | string | 运营商名称 |No|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeIspList** | array[[*NodeIspList*](#NodeIspList)] | 节点运营商列表 |**Yes**|

#### 数据模型


#### NodeIspList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Province** | string | 省份 |No|
| **City** | string | 城市 |No|
| **LineType** | string | 线路类型 |No|
| **IspName** | string | 机房运营商名称 |No|
| **IdcName** | string | 机房名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEdnNodeISP
&ProjectId=kqWOuWek
&IspName=RJjkHYqD
&Province=zYlXuGPl
&City=RSydhxKO
```

### 响应示例
    
```json
{
  "Action": "DescribeUEdnNodeISPResponse",
  "PcOcSet": [
    {
      "City": "uGwAvINF",
      "Isp": "ATsnAkXh",
      "LineType": "StfjJyGk",
      "Province": "jTHjxILr",
      "PyOcName": "qgggmCfn"
    }
  ],
  "RetCode": 0
}
```





