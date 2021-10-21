# 获取文件系统挂载点信息 - DescribeUFSVolumeMountpoint

## 简介

获取文件系统挂载点信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFSVolumeMountpoint)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFSVolumeMountpoint`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VolumeId** | string | 文件系统ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*MountPointInfo*](#MountPointInfo)] |  |**Yes**|
| **TotalMountPointNum** | int | 目前的挂载点总数 |**Yes**|
| **MaxMountPointNum** | int | 文件系统能创建的最大挂载点数目 |**Yes**|

#### 数据模型


#### MountPointInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MountPointName** | string | 挂载点名称 |**Yes**|
| **VpcId** | string | Vpc ID |**Yes**|
| **SubnetId** | string | Subnet ID |**Yes**|
| **MountPointIp** | string | ${挂载点IP}:/ |**Yes**|
| **CreateTime** | int | 文件系统创建时间（unix时间戳） |**Yes**|
| **SubnetDescription** | string | Subnet ID + 网段的形式，方便前端展示 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFSVolumeMountpoint
&Region=cn-zj
&ProjectId=cNJXzsgS
&VolumeId=cfsdTuuj
```

### 响应示例
    
```json
{
  "Action": "DescribeUFSVolumeMountpointResponse",
  "DataSet": [
    "AopLxaqW",
    "PlCXJhDX",
    "ZFZBvcNu",
    "mrOkMEgd"
  ],
  "MaxMountPointNum": 3,
  "RetCode": 0,
  "TotalMountPointNum": 9
}
```





