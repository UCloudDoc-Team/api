# 获取轻量应用主机镜像列表 - DescribeULHostImage

## 简介

获取指定数据中心镜像列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULHostImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ImageType** | string | 镜像类型。标准镜像：Base，应用镜像：App， 自定义镜像：Custom，默认返回所有类型 |No|
| **Scene** | string | 使用场景，当ImageType为"App"时生效。<br />- Normal 常规专区<br />- CrossBorder 跨境专区<br />默认返回所有 |No|
| **OsType** | string | 操作系统类型：Linux， Windows 默认返回所有类型 |No|
| **ImageId** | string | 镜像Id |No|
| **ImageIds.N** | string | 镜像Id列表 |No|
| **Tag** | string | 业务组Id。默认：Default |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的镜像总数 |No|
| **ImageSet** | array[[*ULHostImageSet*](#ULHostImageSet)] | 镜像列表详见 UHostImageSet |No|

#### 数据模型


#### ULHostImageSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区，参见 [可用区列表](api/summary/regionlist)  |No|
| **ImageId** | string | 镜像ID |No|
| **ImageName** | string | 镜像名称 |No|
| **DisplayName** | string | 用于控制台显示的名称 |No|
| **Tag** | string | 业务组 |No|
| **OsType** | string | 操作系统类型：Linux，Windows |No|
| **OsName** | string | 操作系统名称 |No|
| **ImageType** | string | 镜像类型 标准镜像：Base， 行业镜像：Business，自定义镜像：Custom |No|
| **Features** | array[string] | 特殊状态标识，目前包含NetEnhnced（网络增强1.0）, NetEnhanced_Ultra（网络增强2.0）, NetEnhanced_Extreme（网络增强3.0）, HotPlug(热升级), GPU（GPU镜像）,CloudInit, IPv6（支持IPv6网络）,RssdAttachable（支持RSSD云盘）,Vgpu_AMD（支持AMD的vgpu）,Vgpu_NVIDIA（支持NVIDIA的vgpu）,Aarch64_Type（支持arm64架构） |No|
| **IntegratedSoftware** | string | 集成软件名称（仅行业镜像将返回这个值） |No|
| **State** | string | 镜像状态， 可用：Available，制作中：Making， 不可用：Unavailable，复制中：Copying |No|
| **ImageDescription** | string | 镜像描述 |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|
| **ImageSize** | int | 镜像大小 |No|
| **MinimalCPU** | string | 默认值为空'''。当CentOS 7.3/7.4/7.5等镜像会标记为“Broadwell” |No|
| **MaintainEol** | string | 系统EOL的时间，格式：YYYY/MM/DD |No|
| **SceneCategories** | array[string] | 场景分类，目前包含Featured（精选），PreInstalledDrivers（预装驱动），AIPainting（AI绘画），AIModels（AI模型），HPC（高性能计算）  |No|
| **ImageLogoLink** | string | 应用镜像图标url |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULHostImage
&Region=pjGgnjaq
&Zone=ZOVSOArJ
&ProjectId=kxtvkLFX
&ImageType=ejPSbUsC
&FuncType=eCFTVATw
&OsType=viqgVMFv
&ImageId=ufpJpByZ
&ImageIds.N=dfVrUQhG
&Tag=spNxOUpa
&Offset=5
&Limit=7
&PriceSet=1
&Scene=itCvbJFs
```

### 响应示例
    
```json
{
  "Action": "DescribeULHostImageResponse",
  "ImageSet": [
    {
      "CreateTime": 9,
      "Features": [
        "yOUhtYDT"
      ],
      "FuncType": "JsFBJwBE",
      "ImageDescription": "jHIRhqVE",
      "ImageId": "JhriGDJE",
      "ImageName": "cWcSTjUF",
      "ImageSize": 8,
      "ImageType": "xWAfdcfM",
      "IntegratedSoftware": "ECVamgyl",
      "Links": "QrsMIHru",
      "MinimalCPU": "ueFMmxSe",
      "OsName": "skOWUlbZ",
      "OsType": "peesiRDc",
      "State": "mOyOihis",
      "Vendor": "rjrmGMQs",
      "Zone": "BRhIeUvq"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





