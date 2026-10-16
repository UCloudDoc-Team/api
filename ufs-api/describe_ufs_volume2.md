# 获取文件系统列表 - DescribeUFSVolume2

## 简介

获取文件系统列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFSVolume2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFSVolume2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
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
| **TotalCount** | int | 文件系统总数 |**Yes**|
| **DataSet** | array[[*UFSVolumeInfo2*](#UFSVolumeInfo2)] | 文件系统详细信息列表 |**Yes**|

#### 数据模型


#### UFSVolumeInfo2

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VolumeName** | string | 文件系统名称 |**Yes**|
| **VolumeId** | string | 文件系统ID |**Yes**|
| **TotalMountPointNum** | int | 当前文件系统已创建的挂载点数目 |**Yes**|
| **MaxMountPointNum** | int | 文件系统允许创建的最大挂载点数目 |**Yes**|
| **StorageType** | string | 文件系统存储类型，枚举值，Basic表示容量型，Advanced表示性能型 |**Yes**|
| **ProtocolType** | string | 文件系统协议，枚举值，NFSv3表示NFS V3协议，NFSv4表示NFS V4协议 |**Yes**|
| **Remark** | string | 文件系统备注信息 |No|
| **Tag** | string | 文件系统所属业务组 |No|
| **CreateTime** | int | 文件系统创建时间（unix时间戳） |No|
| **ExpiredTime** | int | 文件系统过期时间（unix时间戳） |No|
| **Size** | int | 文件系统大小，单位GB |No|
| **UsedSize** | int | 文件系统当前使用容量，单位GB |No|
| **IsExpired** | string | 是否过期 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFSVolume2
&Region=cn-zj
&ProjectId=DJpEkpgc
&VolumeId=lhwAtBELNnFFCCtnAZauZUyulVgLTOpIBFF
&Offset=9
&Limit=501
&Zone=cn-zj-01
```

### 响应示例
    
```json
{
  "Action": "DescribeUFSVolume2Response",
  "DataSet": [
    {
      "CreateTime": 8,
      "ExpiredTime": 2,
      "IsExpired": "Yes",
      "MaxMountPointNum": 5,
      "ProtocolType": "NFSv4",
      "Remark": "PQJgSJOQ",
      "Size": 9,
      "StorageType": "Advanced",
      "Tag": "wVoXCOhQ",
      "TotalMountPointNum": 1,
      "UsedSize": 1,
      "VolumeId": "BCUKqVILayBIohkHvMFJcXAukkUgqZMflxt",
      "VolumeName": "qoXVyiHKLrARIxnISVeCmWRTxNCRqkLzfUR"
    },
    {
      "CreateTime": 2,
      "ExpiredTime": 4,
      "IsExpired": "Yes",
      "MaxMountPointNum": 5,
      "ProtocolType": "NFSv4",
      "Remark": "GXBqIxLc",
      "Size": 9,
      "StorageType": "Advanced",
      "Tag": "sxtcHxsh",
      "TotalMountPointNum": 1,
      "UsedSize": 1,
      "VolumeId": "ZxaoxhfYQpkFkQWbHCNEDgBeFjBUcOuRuMH",
      "VolumeName": "pYuTTcTGCFkHYOvfgkMVygwakxSnUPQdcEY"
    },
    {
      "CreateTime": 8,
      "ExpiredTime": 8,
      "IsExpired": "Yes",
      "MaxMountPointNum": 5,
      "ProtocolType": "NFSv4",
      "Remark": "SYHlTMuO",
      "Size": 5,
      "StorageType": "Advanced",
      "Tag": "XJUPznAp",
      "TotalMountPointNum": 1,
      "UsedSize": 1,
      "VolumeId": "AUFUveZpdYaXsFzzHsBhjNsKyweRXxDxfFh",
      "VolumeName": "LCtDHYigQPztASQNomZHEJliBWpEYgjWNrc"
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





