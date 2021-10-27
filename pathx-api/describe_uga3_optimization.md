# 获取全球接入UGA3线路加速优化情况 - DescribeUGA3Optimization

## 简介

获取全球接入UGA3线路加速化情况






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUGA3Optimization)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGA3Optimization`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **AreaCode** | string | 源站AreaCode |**Yes**|
| **TimeRange** | string | 默认一天 ，枚举类型["Hour","Day","Week"] |No|
| **AccelerationArea** | string | 加速大区,默认Global,[<br />    "Global":"全球",<br />    "AP":"亚太",<br />    "EU":"欧洲",<br />    "ME":"中东",<br />    "OA":"大洋洲",<br />    "AF":"非洲",<br />    "NA":"北美洲",<br />    "SA":"南美洲"<br />] |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AccelerationInfos** | array[[*AccelerationInfo*](#AccelerationInfo)] | 加速详情 |No|

#### 数据模型


#### AccelerationInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccelerationArea** | string | 加速大区代码 |**Yes**|
| **AccelerationName** | string | 加速大区名称 |**Yes**|
| **NodeInfo** | array[[*NodeDelays*](#NodeDelays)] | 加速提升情况 |**Yes**|

#### NodeDelays

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Area** | string | 加速区域 |**Yes**|
| **AreaCode** | string | 加速区域Code |**Yes**|
| **CountryCode** | string | 国家代码 |**Yes**|
| **FlagUnicode** | string | 国旗Code |**Yes**|
| **FlagEmoji** | string | 国旗Emoji |**Yes**|
| **Latency** | float | 加速延迟 |**Yes**|
| **LatencyInternet** | float | 公网延迟 |**Yes**|
| **LatencyOptimization** | float | 加速提升比例 |**Yes**|
| **Loss** | float | 加速后丢包率 |**Yes**|
| **LossInternet** | float | 原始丢包率 |**Yes**|
| **LossOptimization** | float | 丢包下降比例 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGA3Optimization
&ProjectId=nVpQtYJx
&AreaCode=KDzrtRKf
&TimaRange=qXsmQbZC
&AccelerationArea=QREADGXC
```

### 响应示例
    
```json
{
  "AccelerationInfos": [
    {
      "AccelerationArea": "wtSVlJqK",
      "AccelerationInfo": [
        {
          "AcceleratedPromotion": 3.65369,
          "Area": "dcqPFdqV",
          "AreaCode": "dsVIayvl",
          "CountryCode": "iRYgOBRq",
          "Delay": 1.57584,
          "DelayDirect": 2.33747,
          "DropPromotion": "duDkFnVv",
          "DropRate": 1.52375,
          "DropRateDirect": 9.41138,
          "FlagEmoji": "VFxWmNDb",
          "FlagUnicode": "VlkTiDxv"
        }
      ],
      "AccelerationName": "CjrBEShY"
    }
  ],
  "Action": "DescribeUGA3OptimizationResponse",
  "Message": "fLxdShgs",
  "RetCode": 0
}
```





