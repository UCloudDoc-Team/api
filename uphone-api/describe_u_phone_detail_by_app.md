# 查询应用所安装的云手机列表 - DescribeUPhoneDetailByApp

## 简介

根据AppId，查询安装该应用的云手机以及相关的应用版本信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneDetailByApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **AppId** | string | 应用的唯一标识ID |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UPhoneWithAppVersion总数 |**Yes**|
| **UPhoneDetails** | array[[*UPhoneDetailInstance*](#UPhoneDetailInstance)] | 带有应用版本的云手机实例，具体参数见数据模型 [UPhoneDetailInstanc](#UPhoneDetailInstanc) |**Yes**|

#### 数据模型


#### UPhoneDetailInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPhoneName** | string | 云手机的名称，不超过65个字符。<br /> |No|
| **UPhoneId** | string | 云手机的唯一标识，不超过32个字节。<br /> |No|
| **UPhoneModelName** | string | 云手机规格名称<br /> |No|
| **CPU** | int | 虚拟CPU核数。<br /> |No|
| **Memory** | int | 内存大小。单位MB<br /> |No|
| **DiskSize** | int | 磁盘大小，单位: GB<br /> |No|
| **Resolution** | string | 分辨率<br /> |No|
| **Refresh** | int | 刷新率<br /> |No|
| **ServerId** | string | 云手机所在的服务器ID，不超过32个字节。<br /> |No|
| **ImageId** | string | 云手机镜像ID，不超过32个字节。<br /> |No|
| **OsType** | string | 云手机镜像系统，如"Android armv8"<br /> |No|
| **State** | string | 云手机状态<br />* 启动中: STARTING; <br />* 运行中: RUNNING; <br />* 关机中: STOPPING; <br />* 关机: STOPPED <br />* 重启中: REBOOTING; <br />* 重置中: RESETTING; <br />* 启动失败: START_FAILED; <br />* 关机失败: STOP_FAILED; <br />* 重启失败: REBOOT_FAILED; <br />* 重置失败: RESET_FAILED; <br />* 未知状态：UNDEFINED或""<br /> |No|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-jinan<br /> |No|
| **CityName** | string | 城市名称，eg:上海二、济南市<br /> |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。<br /> |No|
| **Remark** | string | 备注<br /> |No|
| **AppVersion** | [*AppVersionInstance*](#AppVersionInstance) | 应用版本实例，每项参数可见数据模型 [AppVersionInstance](#AppVersionInstance)<br /> |No|

#### AppVersionInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 应用的唯一标识ID |**Yes**|
| **AppVersionId** | string | 应用版本的唯一标识ID |**Yes**|
| **AppVersionName** | string | 应用版本名。 |**Yes**|
| **PackageName** | string | 应用包名。 |**Yes**|
| **URL** | string | 应用版本相关的Apk文件存放的公网URL地址。<br /> |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **Description** | string | 应用版本描述。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneDetailByApp
&ProjectId=SpxQBlwb
&AppId=HiVSdkoH
&Offset=5
&Limit=3
&CityId=ymRopIeR
&BizType=VkHNMLfE
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneDetailByAppResponse",
  "Message": "vjWWzduH",
  "RetCode": 0,
  "TotalCount": "PGQJugFR",
  "UPhoneDetails": [
    {
      "AppVersion": {},
      "CityId": "IeCIPceo",
      "CityName": "OakEGSye",
      "Cpu": "RyunyFBy",
      "CreateTime": 7,
      "DiskSize": "wkswDbdy",
      "ImageId": "URxKYqUa",
      "Memory": "FivZoeEI",
      "OsType": "AmMKfrOm",
      "Refresh": "EwSCsjxX",
      "Remark": "jnQQsYHk",
      "Resolution": "YEzssGSG",
      "ServerId": "FuIJzFLs",
      "State": "PGTkWoaw",
      "UPhoneId": "vlpMaJdT",
      "UPhoneName": "BdMQoxvc"
    }
  ]
}
```





