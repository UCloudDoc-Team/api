# 开启云手机 - PoweronUPhone

## 简介

启动处于关闭状态的云手机实例









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `PoweronUPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UPhoneIds.N** | string | 【数组】云手机实例的资源ID，调用方式举例：UPhoneIds.0=希望开启的云手机实例1的UPhoneId，UPhoneIds.1=云手机实例2的UPhoneId。 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 任务ID，用来查询当前任务状态 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=PoweronUPhone
&Region=cn-zj
&ProjectId=tCJMzvhb
&ServerId=CkFCwwKk
&CityId=nDVNPYEp
&BizType=DpOWQWJR
```

### 响应示例
    
```json
{
  "Action": "PoweronUPhoneResponse",
  "JobId": "KYlhxdzQ",
  "Message": "ZTczRxBh",
  "RetCode": 0
}
```





