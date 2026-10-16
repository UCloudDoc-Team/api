# 获取应用版本列表 - DescribeUPhoneAppVersion

## 简介

获取应用版本列表。

?> AppVersionInstance的VersionName和PackageName需在该应用版本安装之后才能获得







## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneAppVersion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **AppVersionIds.N** | string | 【数组】应用版本的唯一标识 ID，调用方式举例：AppVersionIds.0=希望获取应用版本信息的应用版本 1，AppVersionIds.1=应用版本 2。 如果不传入，则返回当前 城市 所有符合条件的应用版本列表。 |No|
| **AppId** | string | 应用的唯一标识ID |No|
| **UPhoneId** | string | 云手机Id。此参数表示查询手机上所安装的应用版本。 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | AppVersionInstance总数 |**Yes**|
| **AppVersions** | array[[*AppVersionInstance*](#AppVersionInstance)] | 云手机应用版本实例列表，每项参数可见数据模型 [AppVersionInstance](#AppVersionInstance) |**Yes**|

#### 数据模型


#### AppVersionInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 应用的唯一标识ID |**Yes**|
| **AppVersionId** | string | 应用版本的唯一标识ID |**Yes**|
| **AppVersionName** | string | 应用版本名。 |**Yes**|
| **PackageName** | string | 应用包名。 |**Yes**|
| **URL** | string | 应用版本相关的Apk文件存放的公网URL地址。<br /> |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **Description** | string | 应用版本描述。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneAppVersion
&Region=cn-zj
&ProjectId=YYfAwwhT
&AppVersionIds.N=QzopOiKg
&Offset=8
&Limit=5
&AppId=BbdiEyEM
&UPhoneId=VQNCBJxd
&Type=tTnFrkpv
&BizType=YVZSXzFk
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneAppVersionResponse",
  "AppVersions": [
    {
      "AppId": "SEjKWBTm",
      "AppVersionId": "TmodzCSv",
      "CreateTime": "uuHAXsqi",
      "Description": "NNOAbXjb",
      "ModifyTime": "AUkwvbsZ",
      "PackageName": "GawsLtPJ",
      "US3URL": "gzhIUYOG",
      "VersionName": "RgqgxrPU"
    }
  ],
  "Message": "ltzcAIdb",
  "RetCode": 0,
  "TotalCount": 8
}
```





