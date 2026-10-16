# 获取机柜信息列表 - GetRackListV2

## 简介

获取机柜信息列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetRackListV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetRackListV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Limit** | int | 返回数据长度，默认值 20 |No|
| **Offset** | int | 列表起始位置偏移量，默认值 0 |No|
| **RackNum** | string | 机柜编号 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RackList** | array[[*RackList*](#RackList)] | 机柜信息列表 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### RackList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CompanyId** | int | 公司ID |**Yes**|
| **Id** | string | Id |**Yes**|
| **LogicalName** | string | 逻辑机房名 |**Yes**|
| **Number** | string | 机柜编号 |**Yes**|
| **OrganizationId** | int | 项目Id |**Yes**|
| **PhysicalName** | string | 物理机房 |**Yes**|
| **Status** | int | 状态 |**Yes**|
| **CompanyName** | string | 公司名称 |No|
| **PhysicalNameCN** | string | 物理机房中文名称 |No|
| **PowerOnTime** | int | 开电计费时间 |No|
| **ShortId** | string | 短资源id |No|
| **ZoneCn** | string | 可用区 |No|
| **BookPayTimes** | int | 预留计费时间 |No|
| **Manager** | string | 客户经理 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetRackListV2
&Region=cn-zj
&Zone=cn-zj-01
&Limit=9
&Offset=5
&CompanyId=2
&RackNum=VJEROmhJ
&Region=SBEZzmjc
&Zone=pGcCNljq
&ProjectId=aeYhrSuw
```

### 响应示例
    
```json
{
  "Action": "GetRackListV2Response",
  "RackList": [
    {
      "BookPayTimes": 1,
      "CompanyId": 9,
      "CompanyName": "smpiGjaO",
      "Id": "BuTZhQYe",
      "LogicalName": "POVwikve",
      "Manager": "RyGhnEfI",
      "Number": "nTWOsCTe",
      "OrganizationId": 4,
      "PhysicalName": "HSEPJxfk",
      "PhysicalNameCN": "NlSkyavG",
      "PowerOnTime": 7,
      "ShortId": "aMVnDvut",
      "Status": 7,
      "ZoneCn": "ZZMsngyy"
    }
  ],
  "RetCode": 0,
  "TotalCount": 6
}
```





