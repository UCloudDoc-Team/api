# 获取镜像列表 - GetUvodnImage

## 简介

uodn2.0

?> 无

!> 无




## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUvodnImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ImageType** | string | 镜像类型：1标准镜像，2行业镜像，3自定义镜像 |No|
| **Offset** | int | 数据偏移量，默认0，非负整数 |No|
| **Limit** | int | 返回数据长度， 默认20，非负整数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageList** | array[[*ImageInfo*](#ImageInfo)] | 获取的镜像信息，具体参考下面ImageInfo |No|
| **TotalCount** | int | 镜像总数 |No|

#### 数据模型


#### ImageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ImageId** | string | 镜像ID |No|
| **ImageName** | string | 镜像名称 |No|
| **ImageType** | string | 镜像类型：1标准镜像，2行业镜像，3自定义镜像 |No|
| **OcType** | string | 系统类型：unix, windows |No|
| **ImageDesc** | string | 镜像描述 |No|
| **State** | string | 镜像状态：镜像状态 1可用，2不可用 |No|
| **ImageSize** | string | 镜像大小，单位GB |No|
| **CreateTime** | string | 镜像创建时间戳 |No|
| **DeployInfoList** | array[[*DeployImageInfo*](#DeployImageInfo)] | 部署详情列表 |No|

#### DeployImageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IdcId** | string | 机房ID |No|
| **State** | int | 镜像状态 1-可用, 2-不可用, 3-获取中, 4-转换中, 5-部署中 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUvodnImage
&ProjectId=org-xxx
&ImageType=1
```

### 响应示例
    
```json
{
  "Action": "GetUvodnImageResponse",
  "ImageList": [
    {
      "ImageId": "uodn-image-xxx",
      "ImageName": "CentOS 7.2 64位",
      "ImageType": 1,
      "OcType": "CentOs"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





