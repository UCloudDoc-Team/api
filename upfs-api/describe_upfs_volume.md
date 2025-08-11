# 获取UPFS文件系统列表 - DescribeUPFSVolume

## 简介

获取UPFS文件系统列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUPFSVolume)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPFSVolume`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VolumeId** | string | 文件系统ID |No|
| **Offset** | int | 文件列表起始 |No|
| **Limit** | int | 文件列表长度 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UPFS文件系统总数 |**Yes**|
| **DataSet** | array[[*UPFSVolumeInfo*](#UPFSVolumeInfo)] | UPFS文件系统详细信息列表 |**Yes**|

#### 数据模型


#### UPFSVolumeInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区名字 |No|
| **VolumeName** | string | 文件系统名称 |No|
| **VolumeId** | string | 文件系统ID |No|
| **ProtocolType** | string | 文件系统协议类型 |No|
| **Remark** | string | 文件系统备注信息 |No|
| **Tag** | string | 文件系统所属业务组 |No|
| **CreateTime** | int | 文件系统创建时间（unix时间戳） |No|
| **ExpiredTime** | int | 文件系统过期时间（unix时间戳） |No|
| **Size** | int | 文件系统大小，单位GB |No|
| **IsExpired** | string | 是否过期 |No|
| **ChargeType** | string | 计费类型 |No|
| **MountStatus** | int | 文件系统挂载状态 |No|
| **MountAddress** | string | 文件系统挂载地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPFSVolume
&Region=cn-zj
&ProjectId=yDBpseTQ
&VolumeId=TMblQHoJuoOViGPsxOzfCtimAOCeONyujjXRnMHtgKuOIlzsvtJLbrVhbTBLtaZWhxMeAbTNvLhwPwNoLOrguQbIjeFDVXngioewkQwYNtmlgGLIGKCbwntzeXhQvYuHmZCktKYWFKjeyJGrqtaEVSlckMDnPuFSAizSKtzGbmKAdxoJKdPpmvFKbHVLDFrHmoKAJxMGYiBDkZcLDUklvJQvDcDASEDLSQVqAwaLrLKVMXyJzrPcZiznAJImcadPjYrUfqCMpglWQJKrqFibFIoOtyDGUNDpBRQpfZVeSYYeqpazuJCXUSQvuWReyNJNyXvKHQZaOjWX
&Offset=9
&Limit=5500
&Zone=kvsqAKXH
```

### 响应示例
    
```json
{
  "Action": "DescribeUPFSVolumeResponse",
  "DataSet": [
    {
      "CreateTime": 2,
      "ExpiredTime": 6,
      "IsExpired": "Yes",
      "MaxMountPointNum": 1,
      "ProtocolType": "eunAkFuF",
      "Remark": "xOwtCWxh",
      "Size": 2,
      "StorageType": "OLslEoSV",
      "Tag": "eAfYVwJb",
      "TotalMountPointNum": null,
      "UsedSize": 3,
      "VolumeId": "HPcVtkAkOkKSBnNPIjNaoIHJaFdoKcQZzRQcmbmBLGRySWEOXkoyiBUOxLaGFUtJKuCCzcbAoowEhgpGlwVQklcZdYIIwGEPjCmeOtGTCWXLdLdLnfPmODNcPhhlyLYBBRzHXbssTxDinSvGayMRwOEDCNMwPlpatJXDEIwAOtqCDXtqcTBNRKuDcKiIqvIgeFfRywlpklfJdxRfSTZyGVtzLcroNtAEIvJNlwkOYucGgOElBHRsAtFdKLFVoqGSusXZapuaLdaGyXclMlKAnFwpWUJzhmnfRhQullBDAmgwpfPCgqWrpyoggMRLynuAAXoFEhNWmOnX",
      "VolumeName": "wjbRdupnGmtmhStkWotqmfpdeZiBdFKsryWilyrxdWOSvSrUCYtPsrPcoRDcGZDmRHKlFhtfCMzgMcpvkQhrZmTsJIGGJJsvXtTvFrUmYBZbIUCaLYuKCaBxncVLHRgDkiItSrnFXsHeTeTXJFxTHLevCivCbOAeuhTUGPdnJuOkrGtXgsgXBwwHRBugBYCBksHviLakfuzkBCHWlhkyvrhGxJGjlizZfBuJgBIRabebYwPKpnfvkRXgTdGXZPdFkiMowDqAotTfgcUtESmmuGbtiUpLXXauwliEbOeBluIBFYSMCEILRJHFPoynzxrDcwFBOopHyksQ"
    }
  ],
  "RetCode": 0,
  "TotalCount": 7
}
```





