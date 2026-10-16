# 获取物理机价格 - GetPHostPrice

## 简介

获取物理机价格列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetPHostPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetPHostPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Count** | int | 购买数量，范围[1-5] |**Yes**|
| **ChargeType** | string | 计费模式，枚举值为： Year/Month |**Yes**|
| **Quantity** | int | 购买时长，1-10个月或1-10年；默认值为1。月付时，此参数传0，代表购买至月末，1代表整月。 |**Yes**|
| **Cluster** | string | 网络环境，可选千兆：1G ；万兆：10G；25G网络：25G。 |No|
| **Type** | string | 默认为：DB(数据库型)，可以通过接口 [DescribePHostMachineType](api/uphost-api/describe_phost_machine_type.html)获取 |No|
| **Disks.N.IsBoot** | string | 裸金属机型参数->枚举值：<br /><br /> > True，是系统盘 <br /><br /> > False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |No|
| **Disks.N.Type** | string | 裸金属机型参数->磁盘类型：枚举值：CLOUD_RSSD |No|
| **Disks.N.Size** | string | 裸金属机型参数->磁盘大小，单位GB，必须是10GB的整数倍。系统盘20-500GB。数据盘是20-32000G。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*PHostPriceSet*](#PHostPriceSet)] | 价格列表 见 PHostPriceSet |No|

#### 数据模型


#### PHostPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year/Month |No|
| **Price** | float | 价格, 单位:元, 保留小数点后两位有效数字 |No|
| **Product** | string | 枚举值：phost=>为主机价格，如果是云盘包括了系统盘价格。cloudDisk=>所有数据盘价格，只是裸金属机型才返回此参数。 |No|
| **OriginalPrice** | float | 原价格, 单位:元, 保留小数点后两位有效数字 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetPHostPrice
&Region=DHGABXYf
&Zone=MIihxhSa
&ProjectId=ravaeUSs
&Count=1
&ChargeType=mlmlOvKM
&Quantity=5
&Cluster=zEgKSHSm
&Type=TVJcMiGe
&Disks.N.IsBoot=NApaxNYL
&Disks.N.Type=TnjCDKxx
&Disks.N.Size=lTqTywwH
```

### 响应示例
    
```json
{
  "Action": "GetPHostPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "jAhLLbuU",
      "OriginalPrice": 1.77893,
      "Price": 2.14214,
      "Product": "EnLhGNVP"
    }
  ],
  "RetCode": 0
}
```





