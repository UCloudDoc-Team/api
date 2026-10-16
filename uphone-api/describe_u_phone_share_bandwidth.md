# 获取共享带宽列表 - DescribeUPhoneShareBandwidth

## 简介

获取共享带宽列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneShareBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Region** | string | 绑定的目的地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)；不传代表获取所有区域 |**Yes**|
| **ShareBandwidthId** | string | 共享带宽ID，不传表示获取所有共享带宽信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ShareBandwidth** | array[[*ShareBandwidthInfo*](#ShareBandwidthInfo)] | 共享带宽信息 |**Yes**|
| **TotalCount** | int | 共享带宽总数量 |No|

#### 数据模型


#### ShareBandwidthInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 绑定的目的地域。参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | 共享带宽ID |**Yes**|
| **IpProportion** | int | 云手机IP绑定比例 |**Yes**|
| **Bandwidth** | int | 带宽大小，单位M |**Yes**|
| **Name** | string | 共享带宽名称 |No|
| **IpCount** | int | 当前绑定IP数量 |No|
| **BindCount** | int | 当前绑定手机数量 |No|
| **RemainCount** | int | 剩余可绑定手机数量 |No|
| **Remark** | string | 备注 |No|
| **CreateTime** | int | 创建时间；格式为Unix时间戳 |No|
| **ExpireTime** | int | 到期时间；格式为Unix时间戳 |No|
| **ChargeType** | string | 计费模式。枚举值为： > 年 Year，按年付费； > Month，按月付费； > Dynamic，按小时预付费; 默认为月付 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneShareBandwidth
&ProjectId=EChibesN
&Region=bGzGzjUL
&CityId=zliHSacZ
&ShareBandwidthId=HzjzWfis
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneShareBandwidthResponse",
  "Message": "aLFYgvVR",
  "RetCode": 0,
  "ShareBandwidth": [
    {
      "Bandwidth": 5.89288,
      "BindCount": 3,
      "CreateTime": 9,
      "Description": "pINswSvq",
      "ExpireTime": 1,
      "Id": "ZUBaDlXN",
      "IpCount": 4,
      "IpProportion": 3,
      "Name": "aZbmvEvg",
      "Region": "XRloyIxz",
      "RemainCount": 7
    }
  ],
  "TotalCount": 2
}
```





