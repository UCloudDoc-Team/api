# 查询 IP 是否归属 CDN - DescribeULiveIPListInfo

## 简介

查询 IP 是否归属 CDN






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeULiveIPListInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULiveIPListInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **IP** | string | ip列表字符串,示例0.0.0.0,1.1.1.1,最多支持50个ip查询，每个ip使用 , 分隔。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IpSet** | array[[*IpSet*](#IpSet)] | ip归属表 |No|

#### 数据模型


#### IpSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | ip |**Yes**|
| **CdnIp** | boolean | 是否归属于ucloud |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULiveIPListInfo
&ProjectId=ORjngcAx
&IP=svVYLPKR
```

### 响应示例
    
```json
{
  "Action": "DescribeULiveIPListInfoResponse",
  "IpSet": [
    {
      "CdnIp": true,
      "IP": "mxsZVZyp"
    }
  ],
  "RetCode": 0
}
```





