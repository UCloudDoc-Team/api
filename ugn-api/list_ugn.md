# 获取云联网资源列表 - ListUGN

## 简介

获取当前项目下所有云联网资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUGN)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUGN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Limit** | int | 分页大小，默认20 |No|
| **Offset** | int | 偏移量，默认0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGNs** | array[[*UGN*](#UGN)] |  |**Yes**|
| **TotalCount** | int |  |No|
| **Offset** | int |  |No|
| **Limit** | int |  |No|

#### 数据模型


#### UGN

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGNID** | string | 云联网资源 ID |**Yes**|
| **Name** | string | 云联网名称 |**Yes**|
| **Remark** | string | 云联网备注 |**Yes**|
| **CreateTime** | int | 云联网创建时间 |**Yes**|
| **NetworkCount** | int | 关联网络实例数量 |**Yes**|
| **BwPackageCount** | int | 绑定带宽包数量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGNLists
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=Uwdjwjay
&PageSize=8
&Page=6
&UGNID=WwZYkmsO
&ProjectId=WjWMQqHg
```

### 响应示例
    
```json
{
  "Action": "ListUGNResponse",
  "Instances": [
    {
      "CreateTime": 5,
      "Instances": [
        "NMwjIrsh"
      ],
      "InterRegionBandwidths": [
        "fVZVRYGy"
      ],
      "Name": "jVivsVdF",
      "Remark": "aNvxOLBM",
      "RouteRules": [
        "KlTczjrb"
      ],
      "Tag": "vebDnrWg",
      "UGNId": "SdLBDxvC"
    }
  ],
  "Message": "PQjUPsBS",
  "Page": 3,
  "PageSize": 5,
  "RetCode": 0,
  "TotalCount": 4
}
```





