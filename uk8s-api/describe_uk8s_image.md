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
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageSet** | array[[*ImageInfo*](#ImageInfo)] | 虚拟机可用镜像集合, 详见ImageInfo 数组 |No|
| **PHostImageSet** | array[[*ImageInfo*](#ImageInfo)] | 物理机可用镜像集合, 详见ImageInfo 数组 |No|

#### 数据模型


#### ImageInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ZoneId** | int | 可用区 Id |**Yes**|
| **ImageId** | string | 镜像 Id |**Yes**|
| **ImageName** | string | 镜像名称 |**Yes**|
| **NotSupportGPU** | boolean | 该镜像是否支持GPU机型，枚举值[true:不支持，false:支持]。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUK8SImage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=sUDxutjf
```

### 响应示例
    
```json
{
  "Action": "DescribeUK8SImageResponse",
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





