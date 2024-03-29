# 上传文件 - ImportFile

## 简介

上传文件到云手机目录/sdcard/Download/并自动安装APK文件









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ImportFile`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UPhoneIds.N** | string | 云手机ID |**Yes**|
| **FileName** | string | 文件名 |**Yes**|
| **URL** | string | 文件下载链接 |**Yes**|
| **CityId** | string | 城市。 参见 [云手机城市列表](https://docs.ucloud.cn/api/uphone-api/describe_u_phone_cities) |No|
| **ProductType** | string | 枚举值。表示当前操作的产品类型，目前固定值【uphone】，表示云手机场景。 |No|
| **ABI** | string | 上传文件为apk时，可强制指定32位还是64位运行<br />。armeabi-v7a（32位）;不填为系统默认值（64位） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 请求的唯一标识Id，`RetCode`为0时返回，可根据此ID查询请求的执行状态 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ImportFile
&ProjectId=KwCVyyKy
&CityId=Year
&UPhoneId=oGeifdDL
&FileName=IicYFYoh
&File=nZcVXJQG
&Object=XdZzkRse
&BizType=srJzYcdC
&ABI=jjmwmCad
```

### 响应示例
    
```json
{
  "Action": "ImportFileResponse",
  "JobId": "DOztYVbc",
  "RetCode": 0
}
```





