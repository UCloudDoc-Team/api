# 获取社区镜像列表 - DescribeCommunityImages

## 简介

获取社区镜像列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCommunityImages`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CompShareImageId** | string | 镜像Id。支持指定镜像Id查询 |No|
| **Name** | string | 镜像名称。模糊搜索 |No|
| **Author** | string | 搜索指定作者发布的镜像 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | string | 返回数据长度，默认为20，最大100 |No|
| **Tag** | string | 按标签名称搜索，精确匹配 |No|
| **SortCondition.Field** | string | 排序条件。<br />- Favor：按热度排序，获取热点镜像；<br />- PubTime：按发布时间排序，获取最新社区镜像；<br />- Price 按价格排序；<br />- CreatedCount 按使用量排序；<br />默认："PubTime" |No|
| **SortCondition.ASC** | string | 是否升序排列 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageSet** | array[[*CompShareImage*](#CompShareImage)] | 镜像详情列表 |No|
| **TotalCount** | int | 总数量 |No|

#### 数据模型


#### CompShareImage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CompShareImageId** | string | 镜像Id |No|
| **Name** | string | 镜像名称 |No|
| **Author** | string | 镜像作者昵称 |No|
| **AuthInfo** | int | 镜像作者认证信息 |No|
| **ImageOwnerAlias** | string | 镜像来源。<br />- Official 平台镜像；<br />- Community 社区镜像 |No|
| **ImageType** | string | 镜像类型。<br />- System 平台提供的公共镜像；<br />- App 平台提供的应用镜像；<br />- Custom 自制镜像；<br />- Community 社区镜像 |No|
| **IsOfficial** | boolean | 来源是否为官方镜像【仅自制镜像信息返回该字段】 |No|
| **Container** | string | 是否为容器镜像。<br />- True 容器镜像<br />- False 虚机镜像 |No|
| **Status** | string | 镜像状态。<br />- Making 制作中；<br />- Available 可用；<br />- UnAvailable 不可用；<br />- Reviewing 审核中;<br />- Offline 已下线 |No|
| **Size** | int | 镜像大小。单位MB |No|
| **Visibility** | int | 可见性。0：私密镜像；1：公开至镜像社区 |No|
| **Description** | string | 镜像描述信息 |No|
| **Tags** | array[string] | 【array of string】镜像标签 |No|
| **Price** | float | 镜像价格。单位：元 |No|
| **Cover** | string | 镜像封面URL |No|
| **Readme** | string | 镜像详细描述。仅指定镜像Id查询时返回 |No|
| **Softwares** | [*Software*](#Software) | 镜像软件信息 |No|
| **CreatedCount** | int | 镜像引用创建计数 |No|
| **FavoritesCount** | int | 镜像收藏计数 |No|
| **FailedReason** | string | 镜像制作失败错误原因 |No|
| **CreateTime** | int | 创建时间戳 |No|
| **PubTime** | int | 发布时间戳 |No|
| **Owner** | [*Projects*](#Projects) | 镜像所属账号信息 |No|
| **GroupId** | string | 镜像组id |No|
| **VersionName** | string | 版本名称 |No|
| **VersionDesc** | string | 版本描述 |No|
| **SourceGpuType** | string | 自制镜像来源机型 |No|
| **AutoStart** | boolean | 是否支持自启动 default:false |No|
| **ImageCharge** | boolean | 是否镜像收费  default: false |No|
| **ImageUseTime** | int | 镜像使用时长 |No|

#### Software

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Framework** | string | 框架名称 |No|
| **FrameworkVersion** | string | 框架版本 |No|
| **CUDAVersion** | string | CUDA版本 |No|
| **Applications** | array[string] | 【array of string】应用列表 |No|

#### Projects

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccountName** | string | 账号昵称 |No|
| **AccountId** | string | 账号Id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCommunityImages
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lUZpDnwe
&Name=ivgtQEhU
&Author=wDBLKbgn
&SortCondition=pGVSJaJS
&Offset=1
&Limit=nVELQrep
&CompShareImageId=PAuopyLr
&SortCondition.ASC=DrExMweI
&Tag=ZQIlrteO
```

### 响应示例
    
```json
{
  "Action": "DescribeCommunityImagesResponse",
  "ImageSet": [
    {
      "ImageId": "rjroBksO"
    }
  ],
  "RetCode": 0,
  "TotalCount": 8
}
```





