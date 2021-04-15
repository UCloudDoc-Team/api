# 查询跨域带宽 - DescribeInterRegionBandwidth

## 简介

查询跨域带宽









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeInterRegionBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNId** | string | 云联网Id |**Yes**|
| **Offset** | int | 数据偏移量。默认为0 |No|
| **Limit** | int | 数据分页值。默认为20 |No|
| **InterRegionBandwidthIds.N** | string | 跨域带宽Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InterRegionBandwidths** | array[[*InterRegionBandwidth*](#InterRegionBandwidth)] | 跨域带宽信息 |**Yes**|
| **TotalCount** | int | InterRegionBandwidths字段的数量 |No|

#### 数据模型


#### InterRegionBandwidth

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ExpireTime** | int | 到期时间 |**Yes**|
| **UGNId** | string | 云联网Id |**Yes**|
| **InterRegionBandwidthId** | string | 跨域带宽Id |**Yes**|
| **Bandwidth** | int | 带宽（单位为Mb/s） |**Yes**|
| **ChargeType** | string | 计费类型 |**Yes**|
| **Region0** | string | 跨域带宽地域 |**Yes**|
| **Region1** | string | 跨域带宽地域 |**Yes**|
| **PayMode** | string | 付费类型 |**Yes**|
| **State** | int | 跨域带宽状态 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeInterRegionBandwidth
&Zone=cn-zj-01
&ProjectId=ULSXwpkw
&UGNId=imdEPsSn
&InterRegionBandwidthIds.n=JhTrGXWu
&OffSet=8
&Limit=2
```

### 响应示例
    
```json
{
  "Action": "DescribeInterRegionBandwidthResponse",
  "InterRegionBandwidths": [
    {
      "Bandwidth": 9,
      "ChargeType": "Year",
      "CreateTime": 5,
      "ExpireTime": 1,
      "InterRegionBandwidthId": "CAEKJswX",
      "PayMode": "Traffic",
      "Region0": "FFseRXtF",
      "Region1": "jKOISBCu",
      "State": 1,
      "UGNId": "CMMsbcOe"
    }
  ],
  "Message": "success",
  "RetCode": 0,
  "TotalCount": 5
}
```





