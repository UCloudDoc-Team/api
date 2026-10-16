# 获取预留机柜信息 - GetBookRackView

## 简介

获取预留机柜信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetBookRackView)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetBookRackView`                        | **Yes** |
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
| **DataSet** | [*RackBookView*](#RackBookView) | 数据 |No|
| **TotalCount** | int | 是否正常响应：0 - 失败、1 -正常 |No|

#### 数据模型


#### RackBookView

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BookCount** | int | 预留数量 |No|
| **PowerOnCount** | int | 开电数量 |No|
| **RackInfo** | array[[*Rack*](#Rack)] | 机柜信息 |No|

#### Rack

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **CompanyName** | string | 公司名称 |No|
| **Email** | string | 邮箱 |No|
| **Id** | string | id |No|
| **Alias** | string | 机柜别名 |No|
| **Number** | string | 机柜编号 |No|
| **RegionId** | int | 地域id |No|
| **ZoneId** | int | 可用区id |No|
| **Status** | int | 状态(1:初始态，10：已预留，20：开电中，30：已开电，40：改造中，50：关电中，60：已关电，70：开电失败，80：关电失败) |No|
| **AccountId** | int | 账号id |No|
| **CompanyId** | int | 公司id |No|
| **Module** | string | 模块 |No|
| **Battery** | int | 最大电流 |No|
| **Height** | int | 机柜高度 |No|
| **Pdu** | object | pdu参数 |No|
| **Bearer** | int | 承重装置 |No|
| **Picture** | string | 外观图 |No|
| **PictureTime** | int | 拍照时间 |No|
| **PictureStatus** | int | 拍照状态（1：机柜拍照初始态，2：机柜拍照请求中） |No|
| **BookTime** | int | 预留开始时间 |No|
| **BookDeadline** | int | 机柜预留截止时间 |No|
| **BookOffTime** | int | 取消预留时间 |No|
| **PowerOnTime** | int | 开电开始时间 |No|
| **PowerOnDeadline** | int | 用户需求开电时间 |No|
| **PduCost** | float | pdu |No|
| **BatteryCost** | float | 电压价格 |No|
| **BearerCost** | float | 承重装置价格 |No|
| **InclosureCost** | float | 附件价格 |No|
| **CreateTime** | int | 创建时间 |No|
| **UpdateTime** | int | 更新时间 |No|
| **DeleteTime** | int | 删除时间 |No|
| **LongId** | string | 长id |No|
| **ShortId** | string | 短id |No|
| **ChargeType** | int | 计费类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBookRackView
```

### 响应示例
    
```json
{
  "Action": "GetBookRackViewResponse",
  "RetCode": 0,
  "TotalCount": 6
}
```





