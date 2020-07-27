# 查询资源池列表 - DescribeUDSet

## 简介

查询资源池列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDSet)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDSet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **HostIds.N** | string | 资源池的短ID, 如果为空, 则返回当前Region所有资源池的配置信息，否则返回指定资源池的配置信息 |No|
| **Tag** | string | 要查询的业务组名称 |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 返回数据长度, 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的总数 |No|
| **UDSet** | array[[*UDSet*](#UDSet)] | 获取的私有专区资源池列表 |No|

#### 数据模型


#### UDSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 资源池所在可用区 |No|
| **HostId** | string | 资源池的短ID |No|
| **Tag** | string | 业务组名称 |No|
| **Remark** | string | 备注 |No|
| **Name** | string | 实例名称 |No|
| **SN** | string | 资源池的SN号 |No|
| **CreateTime** | int | 创建时间 |No|
| **HostIp** | string | 宿主机ip |No|
| **UHostCount** | int | 主机数量 |No|
| **ChargeType** | string | Year, Month |No|
| **ExpireTime** | int | 到期时间 |No|
| **AutoRenew** | string | 是否自动续费，Yes，No |No|
| **CPU** | int | 虚拟CPU核数, 单位:个 |No|
| **Memory** | int | 内存大小, 单位:MB |No|
| **DiskSpace** | int | 数据盘大小, 单位: GB |No|
| **UsedCPU** | int | 虚拟CPU核数, 单位:个 |No|
| **UsedMem** | int | 内存大小, 单位:MB |No|
| **UsedDisk** | int | 数据盘大小, 单位: GB |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn?Action=DescribeUDSet
&Region=byeHKJgz
&HostIds.n=SFWoBpLC
&Tag=ZsdzeJXh
&Offset=4
&Limit=7
&ProjectId=seTvBjnI
```

### 响应示例
    
```json
{
  "Action": "DescribeUDSetResponse",
  "RetCode": 0,
  "TotalCount": 1,
  "UDSet": [
    {
      "AutoRenew": "True",
      "CPU": 32,
      "ChargeType": "Year",
      "CreateTime": 1544521079,
      "DiskSpace": 4096,
      "ExpireTime": 1544521080,
      "HostId": "udset-xxxx",
      "HostIp": "10.10.10.10",
      "Memory": 131072,
      "Name": "",
      "Remark": "",
      "SN": "SN10231231421",
      "Tag": "Default",
      "UHostCount": 0,
      "UsedCPU": 0,
      "UsedDisk": 0,
      "UsedMem": 0,
      "Zone": "cn-bj2-04"
    }
  ]
}
```





