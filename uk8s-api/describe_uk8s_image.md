# 获取可用镜像 - DescribeUK8SImage

## 简介

获取UK8S支持的Node节点操作系统，可基于该操作系统制定自定义镜像









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUK8SImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ProductType** | string | 产品类型，可选值uhost、uphost，不填则返回所有 |No|
| **MachineType** | string | 适用机型，如O、G、OPRO等，默认为O |No|
| **GPUType** | string | 适用GPU类型，如1080Ti、4090、V100、A800等，MachineType为G时必须提供 |No|
| **K8sVersion** | string | k8s集群版本，如1.28.15 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageSet** | array[[*ImageInfo*](#ImageInfo)] | 虚拟机可用镜像集合, 详见ImageInfo 数组 |No|
| **PHostImageSet** | array[[*ImageInfo*](#ImageInfo)] | 裸金属可用镜像集合, 详见ImageInfo 数组 |No|
| **CustomImageSet** | array[[*ImageInfo*](#ImageInfo)] | 虚拟机自制可用镜像集合, 详见ImageInfo 数组 |No|
| **CustomPHostImageSet** | array[[*ImageInfo*](#ImageInfo)] | 裸金属自制可用镜像集合, 详见ImageInfo 数组 |No|

#### 数据模型


#### ImageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ZoneId** | int | 可用区 Id |**Yes**|
| **ImageId** | string | 镜像 Id |**Yes**|
| **ImageName** | string | 镜像名称 |**Yes**|
| **NotSupportGPU** | boolean | 该镜像是否支持GPU机型，枚举值[true:不支持，false:支持]。 |**Yes**|
| **OsType** | string | OS 类型 |**Yes**|
| **OsName** | string | OS 名称 |**Yes**|
| **Features** | array[string] | 镜像支持的特性 |No|
| **ImageSize** | int | 镜像大小 |No|
| **IntegratedSoftware** | string | 集成软件名称, 如NV驱动版本、cuda版本 |No|
| **SupportedGPUTypes** | array[string] | 支持的GPU机型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUK8SImage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=sUDxutjf
&ProductType=TzadjShf
&MachineType=HfHJuJRC
&GPUType=QDBWdeSh
&K8SVersion=VYTIrewq
```

### 响应示例
    
```json
{
  "Action": "DescribeUK8SImageResponse",
  "CustomIImageSet": [
    "vcSXSoOo"
  ],
  "ImageSet": [
    {
      "ImageId": "SOqcWTEJ",
      "ImageName": "hIscEgwy",
      "NotSupportGPU": false,
      "ZoneId": 5
    }
  ],
  "ImageSetnew": [
    {
      "ImageId": "KeQfHnUL",
      "ImageName": "itWRmsMy",
      "NotSupportGPU": true,
      "ZoneId": 5
    }
  ],
  "Message": "RcXlEGbn",
  "PHostCustomIImageSet": [
    "jABaDaml"
  ],
  "PHostImageSet": [
    {
      "ImageId": "yFeQPFUL",
      "ImageName": "OlgivCjk",
      "NotSupportGPU": true,
      "ZoneId": 9
    }
  ],
  "RetCode": 0
}
```





