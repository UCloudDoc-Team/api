# 获取镜像列表 - DescribeImage

## 简介

获取指定数据中心镜像列表，用户可通过指定操作系统类型，镜像Id进行过滤。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeImage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageType** | string | 镜像类型。标准镜像：Base，镜像市场：Business， 自定义镜像：Custom，默认返回所有类型 |No|
| **OsType** | string | 操作系统类型：Linux， Windows 默认返回所有类型 |No|
| **ImageId** | string | 镜像Id |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **PriceSet** | int | 是否返回价格：1返回，0不返回；默认不返回 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的镜像总数 |No|
| **ImageSet** | array[[*UHostImageSet*](#UHostImageSet)] | 镜像列表详见 UHostImageSet |No|

#### 数据模型


#### UHostImageSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，参见 [可用区列表](api/summary/regionlist)  |No|
| **ImageId** | string | 镜像ID |No|
| **ImageName** | string | 镜像名称 |No|
| **OsType** | string | 操作系统类型：Linux，Windows |No|
| **OsName** | string | 操作系统名称 |No|
| **ImageType** | string | 镜像类型 标准镜像：Base， 行业镜像：Business，自定义镜像：Custom |No|
| **Features** | array[string] | 特殊状态标识，目前包含NetEnhnced（网络增强1.0）, NetEnhanced_Ultra（网络增强2.0）, NetEnhanced_Extreme（网络增强3.0）, HotPlug(热升级), GPU（GPU镜像）,CloudInit, IPv6（支持IPv6网络）,RssdAttachable（支持RSSD云盘）,Vgpu_AMD（支持AMD的vgpu）,Vgpu_NVIDIA（支持NVIDIA的vgpu）,Aarch64_Type（支持arm64架构） |No|
| **FuncType** | string | 行业镜像类型（仅行业镜像将返回这个值） |No|
| **IntegratedSoftware** | string | 集成软件名称（仅行业镜像将返回这个值） |No|
| **Vendor** | string | 供应商（仅行业镜像将返回这个值） |No|
| **Links** | string | 介绍链接（仅行业镜像将返回这个值） |No|
| **State** | string | 镜像状态， 可用：Available，制作中：Making， 不可用：Unavailable，复制中：Copying |No|
| **ImageDescription** | string | 镜像描述 |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|
| **ImageSize** | int | 镜像大小 |No|
| **MinimalCPU** | string | 默认值为空'''。当CentOS 7.3/7.4/7.5等镜像会标记为“Broadwell” |No|
| **MaintainEol** | string | 系统EOL的时间，格式：YYYY/MM/DD |No|
| **SupportedGPUTypes** | array[string] | 支持的GPU机型 |No|
| **SceneCategories** | array[string] | 场景分类，目前包含Featured（精选），PreInstalledDrivers（预装驱动），AIPainting（AI绘画），AIModels（AI模型），HPC（高性能计算）  |No|
| **PrimarySoftware** | string | 主要安装软件 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeImage
&Region=PhaAzVTd
&Zone=cqKjGzBc
&ProjectId=COzFsxJJ
&ImageType=gzhDcTIW
&OsType=YKGOVXER
&ImageId=NucmrhHv
&Offset=7
&Limit=3
&PriceSet=8
&FuncType=VQKlDpNp
&FuncType=SKKAirKJ
&FuncType=VSVNRRqM
```

### 响应示例
    
```json
{
  "Action": "DescribeImageResponse",
  "ImageSet": [
    {
      "CreateTime": 7,
      "Features": [
        "fIjpPBic"
      ],
      "FuncType": "HUUNWmIe",
      "ImageDescription": "HVeLQVxc",
      "ImageId": "DSFagZyu",
      "ImageName": "tLrQRsEd",
      "ImageSize": 5,
      "ImageType": "qHUuzcMF",
      "IntegratedSoftware": "IHavDZNf",
      "Links": "fKLwvSib",
      "MinimalCPU": "RDlcZqYK",
      "OsName": "NxoYUnar",
      "OsType": "DxLQCAes",
      "State": "eGSoZznP",
      "Vendor": "JjBqzeus",
      "Zone": "BOUCCxQH"
    }
  ],
  "RetCode": 0,
  "TotalCount": 4
}
```





