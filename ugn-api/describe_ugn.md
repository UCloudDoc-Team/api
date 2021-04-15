# 查询云联网 - DescribeUGN

## 简介

查询云联网









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Offset** | int | 数据偏移量。默认为0 |No|
| **Limit** | int | 数据分页值。默认为20 |No|
| **UGNIds.N** | string | 云联网Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGNs** | array[[*UGN*](#UGN)] | 云联网信息 |No|
| **TotalCount** | int | UGNs字段的数量 |No|

#### 数据模型


#### UGN

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGNId** | string | 云联网Id |**Yes**|
| **Name** | string | 云联网名称 |**Yes**|
| **Remark** | string | 云联网备注 |**Yes**|
| **Tag** | string | 业务组Id |**Yes**|
| **CreateTime** | int | 云联网创建时间 |**Yes**|
| **Instances** | array[string] | 实例Id |**Yes**|
| **RouteRules** | array[string] | 路由规则Id |**Yes**|
| **InterRegionBandwidths** | array[string] | 跨域路由Id |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGN
&ProjectId=zHRJYUtY
&UGNIds.n=WzlapirB
&Offset=6
&Limit=9
```

### 响应示例
    
```json
{
  "Action": "DescribeUGNResponse",
  "Message": "success",
  "RetCode": 0,
  "TotalCount": 5,
  "UGNs": [
    {
      "BusinessId": "TsnlXkXv",
      "CreateTime": "xfYXMGlB",
      "Instances": [
        "lirkotwG"
      ],
      "InterRegionBandwidths": [
        "zCIXBNMx"
      ],
      "Name": "QPttKgzz",
      "Remark": "vckecGys",
      "RouteRules": [
        "ATtxdRPE"
      ],
      "UGNId": "bzdtRtHB"
    }
  ]
}
```





