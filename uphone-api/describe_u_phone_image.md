# 获取云手机镜像信息列表 - DescribeUPhoneImage

## 简介

获取云手机镜像信息列表。  









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | string | 希望获取的镜像类型，枚举值，不传则返回全部类型的镜像： <br /> >标准镜像: BASE; <br />>自制镜像: CUSTOM;  <br /> |No|
| **ImageIds.N** | string | 【数组】云手机镜像资源 ID，调用方式举例：ImageIds.0=希望获取信息的云手机镜像 1，ImageIds.1=云手机镜像 2。 如果不传入，则返回当前 城市 所有符合条件的云手机镜像。 |No|
| **Offset** | string | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 最大返回镜像数量，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Images** | array[[*UPhoneImageInstance*](#UPhoneImageInstance)] | 云手机镜像实例列表，具体参数见 [UPhoneImageInstance](#uphoneimageinstance) |**Yes**|
| **TotalCount** | int | UPhoneImageInstance总数 |No|

#### 数据模型


#### UPhoneImageInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ImageId** | string | 云手机镜像资源Id |**Yes**|
| **ImageName** | string | 云手机镜像名称 |**Yes**|
| **OsType** | string | 云手机镜像系统 |**Yes**|
| **ImageType** | string | 云手机镜像类型，枚举值：<br />> 用户自制镜像: CUSTOM;  <br />> 标准镜像: BASE;;   |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **ImageState** | string | 云手机镜像状态<br />* 制作中: 制作中; <br />* 可用的: CREATING; <br />* 制作失败: CREATE_FAILED; <br />* 上传中: UPLOADING <br />* 上传失败: UPLOAD_FAILED; <br />* 未知状态：UNDEFINED或"" |**Yes**|
| **Description** | string | 云手机镜像描述信息 |No|
| **UPhoneId** | string | 云手机镜像创建时所属云手机资源 Id |No|
| **AppVersions** | array[[*AppVersionInstance*](#AppVersionInstance)] | 云手机镜像所安装的应用版本列表，具体参数见 [AppVersionInstance](#appversioninstance) |No|

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
https://api.ucloud.cn/?Action=DescribeUPhoneImage
&Region=cn-zj
&ProjectId=tnCZcFev
&ImageName=QAQarBGV
&Description=XaDyjuqL
&OsType=FQGJgubs
&Offset=inLKPiri
&Limit=gtUTZvij
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneImageResponse",
  "JobId": "sxZCbrYe",
  "Message": "SaXutTRS",
  "RetCode": 0,
  "TotalCount": 6
}
```





