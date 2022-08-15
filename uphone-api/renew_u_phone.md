# 一键新机 - RenewUPhone

## 简介

修改UPhone的device_id、imei、meid 以及其他相关配置，达到一键新机的效果









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RenewUPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UPhoneIds.N** | string | 【数组】云手机实例的资源 ID，调用方式举例：UPhoneIds.0=希望重启的云手机实例 1 的 UPhoneId，UPhoneIds.1=云手机实例 2 的 UPhoneId。 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|
| **Customize** | boolean | 自定义设备参数设置的开关，true时会读取用户设置的下列设备参数信息；false时随机读取ucloud内置设备参数。默认false |No|
| **Brand** | string | 品牌 |No|
| **Model** | string | 设备型号 |No|
| **Manufacture** | string | 厂商 |No|
| **SerialNumber** | string | 序列号 |No|
| **BaseBand** | string | 基带版本 |No|
| **Board** | string | 主板名 |No|
| **DisplayID** | string | 显示的版本号 |No|
| **Device** | string | 设备名 |No|
| **FingerPrint** | string | 系统指纹 |No|
| **ProductName** | string | 产品名称 |No|
| **BuildID** | string | build的版本号 |No|
| **BuildHost** | string | 固件编译主机 |No|
| **BootLoader** | string | bootloader版本号 |No|
| **BuildTags** | string | 系统标记 |No|
| **BuildVersionInc** | string | 版本增加说明 |No|
| **IMEI** | string | 串号 |No|
| **PhoneNumber** | string | 手机号码 |No|
| **ICCID** | string | SIM卡唯一标识 |No|
| **IMSI** | string | 移动识别码 |No|
| **IMEISV** | string | 移动设备标识码软件 |No|
| **RadioMac** | string | 移动网络mac地址 |No|
| **WiFiName** | string | 当前连接Wi-Fi名称 |No|
| **BSSID** | string | Wi-Fi 物理地址 |No|
| **AndroidID** | string | AOSP唯一标识 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **JobId** | string | 任务ID，用来查询一键新机任务状态 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RenewUPhone
&ProjectId=lCnvAJpT
&CityId=enOKEcYD
&UPhoneIds.N=dtjXmIbu
&Rollback=true
&BizType=atTalMTB
&Customize=true
&Brand=rSASJQfj
&Model=BPXIfoTd
&Manufacture=kIokNumG
&SerialNumber=qoOsqfaS
&BaseBand=oyIHNuQP
&Board=iZEzyZnG
&DisplayID=ckNTlSjK
&Device=morEtbRC
&FingerPrint=czMzTxuA
&ProductName=SSNSoFTV
&BuildID=eGLtsYbZ
&BuildHost=GxIaVKnr
&BootLoader=FfWGcHfx
&BuildTags=QyFFyaZS
&BuildVersionInc=OSuVepQS
&IMEI=QiNMlniy
&AndroidID=LogWjPlP
&PhoneNumber=FrEMKVBC
&ICCID=mXwsnbyG
&IMSI=TzMzfOIK
&IMEISV=reCPUQDn
&RadioMac=PURzLjNY
&WiFiName=QTCucePr
&BSSID=NqfQspRX
&ICCID=KaxvfVLq
&IMSI=duBiSgxx
&IMEISV=LFOyeAZy
&RadioMac=GbwPuJzI
&WiFiName=UqEZmxeE
&BSSID=xLJTUahU
```

### 响应示例
    
```json
{
  "Action": "RenewUPhoneResponse",
  "JobId": "YkXBHxWU",
  "Message": "dpuvBdBp",
  "RetCode": 0
}
```





