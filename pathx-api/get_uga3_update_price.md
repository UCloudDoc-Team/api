# 全球统一接入获取实例更新价格（增加、删退） - GetUGA3UpdatePrice

## 简介

全球统一接入获取实例更新价格（增加、删退）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUGA3UpdatePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUGA3UpdatePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 资源ID |**Yes**|
| **Bandwidth** | int | 只有升级带宽的时候有价格变化 |No|
| **AccelerationArea** | string | 暂未支持，加速大区，在更换加速大区的时候使用 |No|
| **AreaCode** | string | 暂未支持，源站区域 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格 元。大于0需付费，小于0则退费。 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGA3UpdatePrice
&ProjectId=CyXBnfem
&InstanceId=ArNMHLJq
&Bandwidth=9
&AccelerationArea=ZuItZjJC
&AreaCode=NhwZRSHw
&AccelerationArea=JFNAZwpz
&AreaCode=TVSfWmSr
```

### 响应示例
    
```json
{
  "Action": "GetUGA3UpdatePriceResponse",
  "Price": 7.45571,
  "RetCode": 0
}
```





