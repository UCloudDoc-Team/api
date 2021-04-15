# 修改跨域带宽 - ModifyInterRegionBandwidth

## 简介

修改跨域带宽









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyInterRegionBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNId** | string | 云联网Id |**Yes**|
| **InterRegionBandwidthId** | string | 跨域带宽Id |**Yes**|
| **Bandwidth** | string | 带宽（单位为Mb/s） |**Yes**|
| **PayMode** | string | 付费类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyInterRegionBandwidth
&ProjectId=NiaDhxXt
&UGNId=iMCXpihm
&InterRegionBandwidthId=aDaHKJQi
&PayMode=Traffic
&Bandwidth=BhzUGpnq
```

### 响应示例
    
```json
{
  "Action": "ModifyInterRegionBandwidthResponse",
  "Message": "success",
  "RetCode": 0
}
```





