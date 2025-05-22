# 创建文件系统 - CreateUFSVolume

## 简介

创建文件系统






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUFSVolume)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUFSVolume`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 文件系统大小，单位为GB，必须为100的整数倍，容量型Size最小为500GB，性能型文件系统Size最小为100GB |**Yes**|
| **StorageType** | string | 文件系统存储类型，Basic表示容量型，Advanced表示性能型 |**Yes**|
| **ProtocolType** | string | 文件系统协议，目前仅支持NFSv4 |**Yes**|
| **VolumeName** | string | 文件系统名称 |No|
| **Remark** | string | 备注 |No|
| **Tag** | string | 文件系统所属业务组 |No|
| **ChargeType** | string | 计费模式，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费（需开启权限）； Trial，试用（需开启权限） 默认为Dynamic |No|
| **Quantity** | int | 购买时长 默认: 1 |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VolumeName** | string | 文件系统名称 |**Yes**|
| **VolumeId** | string | 文件系统ID |**Yes**|
| **VolumeStatus** | string | 文件系统挂载点状态 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUFSVolume
&VolumeName=saHszswLdzUZzUZsPiwCAnJtBouOgHSzIRb
&ProjectId=MIyyFdSR
&StorageType=Advanced
&ProtocolType=NFSv4
&Size=500
&Zone=cn-zj-01
```

### 响应示例
    
```json
{
  "Action": "CreateUFSVolumeResponse",
  "RetCode": 0,
  "VolumeId": "ufs-xxx",
  "VolumeName": "zUZzUZsPiwCAnJ",
  "VolumeStatus": "UnInitialized"
}
```





