# 获取云手机列表 - DescribeUPhone

## 简介

获取云手机列表信息。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ServerId** | string | 云手机服务器的资源ID。 |No|
| **UPhoneIds.N** | string | 【数组】云手机实例的资源 ID，调用方式举例：UPhoneIds.0=希望获取信息的云手机 1 的 UPhoneId，UPhoneIds.1=云手机实例 2 的 UPhoneId。如果都不传入，则返回当前 城市 所有符合条件的云手机列表。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为200，最大200 |No|
| **Tag** | string | 要查询的业务组名称 |No|
| **IsAll** | boolean | 是否返回全部。如果有此参数，分页不生效。 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UPhoneInstance总数 |**Yes**|
| **UPhones** | array[[*UPhoneInstance*](#UPhoneInstance)] | 云手机实例列表，每项参数可见数据模型 [UPhoneInstance](#UPhoneInstance) |**Yes**|

#### 数据模型


#### UPhoneInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPhoneName** | string | 云手机的名称，不超过65个字符。 |**Yes**|
| **UPhoneId** | string | 云手机的唯一标识，不超过32个字节。 |**Yes**|
| **UPhoneModelName** | string | 云手机规格名称 |**Yes**|
| **CPU** | int | 虚拟CPU核数。 |**Yes**|
| **Memory** | int | 内存大小。单位MB |**Yes**|
| **DiskSize** | int | 磁盘大小，单位: GB |**Yes**|
| **Resolution** | string | 分辨率 |**Yes**|
| **Refresh** | int | 刷新率 |**Yes**|
| **ServerId** | string | 云手机所在的服务器ID，不超过32个字节。 |**Yes**|
| **ImageId** | string | 云手机镜像ID，不超过32个字节。 |**Yes**|
| **OsType** | string | 云手机镜像系统，如"Android armv8" |**Yes**|
| **State** | string | 云手机状态<br />* 启动中: STARTING; <br />* 运行中: RUNNING; <br />* 关机中: STOPPING; <br />* 关机: STOPPED <br />* 重启中: REBOOTING; <br />* 重置中: RESETTING; <br />* 启动失败: START_FAILED; <br />* 关机失败: STOP_FAILED; <br />* 重启失败: REBOOT_FAILED; <br />* 重置失败: RESET_FAILED; <br />* 未知状态：UNDEFINED_STATE或"" |**Yes**|
| **CityId** | string | 城市Id，eg: cn-shanghai, cn-jinan |**Yes**|
| **CityName** | string | 城市名称，eg:上海二、济南市 |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **Tag** | string | 业务组名称<br /> |**Yes**|
| **SplashScreen** | string | 云手机启动图片URL链接 |**Yes**|
| **Callback** | string | 云手机异步任务回调 |**Yes**|
| **Remark** | string | 备注 |No|
| **ChargeType** | string | 计费模式。枚举值为： > 年 Year，按年付费； > Month，按月付费； > Dynamic，按小时预付费; 默认为月付 |No|
| **ExpireTime** | int | 到期时间；格式为Unix时间戳 |No|
| **IpRegion** | string | IP所属地域Id，eg: hk，th-bkk |No|
| **Ip** | string | 云手机IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhone
&Region=cn-zj
&ProjectId=jRiJUtMX
&UPhoneModelNames.N=UhRcfBiN
&Offset=7
&Limit=7
&UPhoneIds.N=afagJlif
&IdcId=vVPrdVit
&CityId=EQvCvWeY
&Tag=KYtleBzj
&IsAll=true
&BizType=lTWBNOpE
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneResponse",
  "Message": "eMHNqXNR",
  "RetCode": 0,
  "TotalCount": 3,
  "UPhoneModels": [
    "kFjyguKQ"
  ]
}
```





