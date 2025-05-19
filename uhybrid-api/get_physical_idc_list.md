# 获取物理机房列表 - GetPhysicalIDCList

## 简介

获取所有机柜关联到物理机房列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetPhysicalIDCList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetPhysicalIDCList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*PhysicalIDCList*](#PhysicalIDCList)] | 机房信息列表 |No|

#### 数据模型


#### PhysicalIDCList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **UUID** | int | 唯一id |**Yes**|
| **PhysicalRegion** | string | 物理机房区域 |**Yes**|
| **LogicalAliasName** | string | 逻辑别名 |**Yes**|
| **LogicalName** | string | 逻辑名 |**Yes**|
| **IDCOperator** | string | IDC 操作人 |**Yes**|
| **NetWorkVersion** | string | 网络版本 |**Yes**|
| **RegionOwner** | string | 所属人 |**Yes**|
| **ExternalName** | string | 外网名称 |**Yes**|
| **IDCMaintainer** | string | idc维护人员 |**Yes**|
| **IDCOperatorContact** | string | 联系方式 |**Yes**|
| **IDCOpeningDate** | string | idc开始使用日期 |**Yes**|
| **City** | string | 城市 |**Yes**|
| **ShowOrder** | int | 显示顺序 |**Yes**|
| **AssetOwnerEmail** | string | 所有者邮箱 |**Yes**|
| **AssetOwner** | string | 所有者姓名 |**Yes**|
| **IDCMaintainerEmail** | string | idc维护人员邮箱 |**Yes**|
| **BizOwner** | string | 商务 |**Yes**|
| **BizOwnerEmail** | string | 商务邮箱 |**Yes**|
| **LocationOperateStatus** | string | 运营状态 |**Yes**|
| **ResourceSeller** | string | 资源卖家 |**Yes**|
| **BusinessType** | string | 资源类型 |**Yes**|
| **AssetFlag** | boolean | 资产标记 |**Yes**|
| **Remark** | string | 备注 |**Yes**|
| **LastUpdatePerson** | string | 最后更新人 |**Yes**|
| **PhysicalNameCN** | string | 物理机房中文名 |No|
| **PhysicalName** | string | 物理机房名称 |No|
| **IDCType** | string | 数据中心类型 |No|
| **RegionId** | string | 地域id |No|
| **AvailableZone** | string | 可用区 |No|
| **ZoneId** | string | 可用区id |No|
| **IDCAddress** | string | idc地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetPhysicalIDCList
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=NiMWAmFx
```

### 响应示例
    
```json
{
  "Action": "GetPhysicalIDCListResponse",
  "Data": [
    "XKCCiDvi"
  ],
  "RetCode": 0
}
```





