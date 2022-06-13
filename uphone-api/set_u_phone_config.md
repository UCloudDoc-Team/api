# 设置云手机参数 - SetUPhoneConfig

## 简介

设置云手机画面参数（分辨率、DPI、帧率、码率）









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SetUPhoneConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **UPhoneIds.N** | string | 【数组】云手机实例的资源 ID，调用方式举例：UPhoneIds.0=云手机实例 1 的 UPhoneId，UPhoneIds.1=云手机实例 2 的 UPhoneId。 |**Yes**|
| **Resolution** | string | 云手机画面分辨率（宽x高） （例，1920x1080，中间是字母x）宽和高的取值范围[100,5000] |No|
| **Refresh** | string | 云手机画面刷新率，即帧率（例，30）取值范围[1,200] |No|
| **Bitrate** | string | 云手机画面传输码率（例，8000）取值范围[100,50000] |No|
| **Async** | string | 异步请求开关，只有为1的时候才是异步，不填或者其他数值为同步 |No|
| **Dpi** | string | 云手机dpi，取值范围[100,1000] |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RequestId** | string | request_uuid，唯一值，用于区分request |**Yes**|
| **JobId** | string | 异步请求成功后返回JobId，用以查询Job状态 |No|
| **Results** | array[[*Results*](#Results)] | 同步请求会返回命令行结果，异步请求该参数为空 |No|

#### 数据模型


#### Results

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ExecuteMsg** | string |  |No|
| **UPhoneId** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SetUPhoneConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=oPIXPoSJ
&CityId=DApbIrxQ
&UPhoneIds.N=HOaFSIhP
&Resolution=oHyPROle
&Refresh=1
&Bitrate=5
&Async=pMmzRdxY
&DPI=DSpKnGec
&BizType=ZgLHmWuT
```

### 响应示例
    
```json
{
  "Action": "SetUPhoneConfigResponse",
  "JobId": "oFdfglTZ",
  "Message": "mKFJCITd",
  "Results": [
    "ImxKesjU"
  ],
  "RetCode": 0
}
```





