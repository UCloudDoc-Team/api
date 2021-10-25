# 创建全球统一接入加速配置项 - CreateUGA3Instance

## 简介

创建全球统一接入加速配置项






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGA3Instance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGA3Instance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Bandwidth** | string | 实例的共享带宽 |**Yes**|
| **Name** | string | 加速配置实例名称,默认PathX |No|
| **AreaCode** | string | 非必填,如果不填，会根据Domain 和IPList 去选一个最近的源站区域<br />BKK表示AreaCode;曼谷表示Area<br />["BKK":"曼谷","DXB":"迪拜","FRA":"法兰克福","SGN":"胡志明市","HKG":"香港",CGK":"雅加达","LOS":"拉各斯","LHR":"伦敦","LAX":"洛杉矶","MNL":"马尼拉","DME":"莫斯科","BOM":"孟买","MSP":"圣保罗","ICN":"首尔","PVG":"上海","SIN":"新加坡","NRT":"东京","IAD":"华盛顿","TPE": "台北"] |No|
| **Remark** | string | 备注项 |No|
| **ChargeType** | string | 支付方式，如按月、按年、按时 |No|
| **Quantity** | int | 购买周期 |No|
| **AccelerationArea** | string | 加速大区,默认Global,[<br />    "Global":"全球",<br />    "AP":"亚太",<br />    "EU":"欧洲",<br />    "ME":"中东",<br />    "OA":"大洋洲",<br />    "AF":"非洲",<br />    "NA":"北美洲",<br />    "SA":"南美洲"<br />] |No|
| **OriginIPList** | string | 加速源IP，多个IP用英文半角逗号(,)隔开；IPList和Domain二选一必填 |No|
| **OriginDomain** | string | 加速源域名，IPList和Domain二选一必填 |No|
| **CouponId** | string | 使用代金券可冲抵部分费用，仅全地域可用的代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 加速配置ID |**Yes**|
| **CName** | string | 加速域名 用户可把业务域名CName到此域名上 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGA3Instance
&ProjectId=nokLynpU
&Name=khlbkxgH
&Bandwidth=LJDpaNhT
&Area=KOVfnTrl
&AreaCode=ZcIURsAI
&IPList=LsDrTIzh
&Domain=qygdVyTi
&Remark=tPzdbmKS
&ChargeType=WpMYGAAo
&Quantity=4
&CouponId=UweunqVX
&AccelerationArea=gTIRBRak
```

### 响应示例
    
```json
{
  "Action": "CreateUGA3InstanceResponse",
  "CName": "uaFuGcxI",
  "InstanceId": "ppNTpbvF",
  "Message": "ueuySWBx",
  "RetCode": 0
}
```





