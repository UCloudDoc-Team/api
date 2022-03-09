# 获取账单明细 - ListUBillDetail

## 简介

获取某个账期内的所有消费。

?> 获取当月账单明细一般存在一天延迟。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUBillDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BillingCycle** | string | 账期，YYYY-MM，比如2021-08，只支持2018-05之后的查询 |**Yes**|
| **ProjectName** | string | 项目名称 (筛选项, 默认全部)	 |No|
| **ResourceIds.N** | string | 资源ID(筛选项, 默认全部)	<br />支持多筛选，多筛选请在请求参数中添加多个字段<br />例<br />ResourceIds.0: uhost-bzgf1gh5，<br />ResourceIds.1: uhost-gu1xpspa，<br /> |No|
| **OrderType** | string | 订单类型 (筛选项, 默认全部) 。枚举值：<br /><br /> > OT_BUY:新购 <br /><br /> > OT_RENEW:续费 <br /><br /> > OT_UPGRADE:升级 <br /><br /> > OT_REFUND:退费 <br /><br /> > OT_DOWNGRADE:降级 <br /><br /> > OT_ADDITIONAL:补单 <br /><br /> > OT_SUSPEND:结算 <br /><br /> > OT_PAYMENT:删除资源回款 <br /><br /> > OT_POSTPAID_PAYMENT:后付费回款 <br /><br /> > OT_RECOVER:删除恢复 <br /><br /> > OT_POSTPAID_RENEW:过期续费回款 |No|
| **ChargeType** | string | 计费方式 (筛选项, 默认全部)。枚举值：<br /><br /> > Dynamic:按时 <br /><br /> > Month:按月 <br /><br /> > Year:按年 <br /><br /> > Once:一次性按量 <br /><br /> > Trial:试用 <br /><br /> > Donate:赠送 <br /><br /> > Used:按量 <br /><br /> > Post:后付费 <br /><br /> > Day:按天 <br /><br /> > Quarter:按季度 <br /><br /> > Semester:按半年 |No|
| **ShowZero** | int | 是否显示0元订单 (0 不显示, 1 显示, 默认0) |No|
| **PaidState** | int | 支付状态 (筛选项, 1:仅显示未支付订单; 2:仅显示已支付订单; 0:两者都显示)	 |No|
| **UserEmail** | string | 用户邮箱，可以根据用户邮箱来进行筛选 |No|
| **Limit** | int | 每页数量，默认值25，最大值：100。 |No|
| **Offset** | int | 数据偏移量 (默认0)	 |No|
| **ResourceTypes.N** | string | 产品类型 (筛选项, 默认全部),<br />支持多筛选，多筛选请在请求参数中添加多个字段。枚举值：<br /><br /> > uhost:云主机 <br /><br /> > udisk:普通云硬盘 <br /><br /> > udb:云数据库 <br /><br /> > eip:弹性IP <br /><br /> > ufile:对象存储 <br /><br /> > fortress_host:堡垒机 <br /><br /> > ufs:文件存储 <br /><br /> > waf:WEB应用防火墙 <br /><br /> > ues:弹性搜索 <br /><br /> > udisk_ssd:SSD云硬盘 <br /><br /> > rssd:RSSD云硬盘 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Items** | array[[*BillDetailItem*](#BillDetailItem)] | 账单明细数组 |**Yes**|
| **TotalCount** | int | 账单明细总长度 |**Yes**|

#### 数据模型


#### BillDetailItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Amount** | string | 订单总金额 |**Yes**|
| **AmountReal** | string | 现金账户支付 |**Yes**|
| **AmountFree** | string | 赠送金额抵扣 |**Yes**|
| **AmountCoupon** | string | 代金券抵扣 |**Yes**|
| **AzGroupCName** | string | 可用区 |**Yes**|
| **ChargeType** | string | 计费方式。枚举值：<br /><br /> > Dynamic:按时 <br /><br /> > Month:按月 <br /><br /> > Year:按年 <br /><br /> > Once:一次性按量 <br /><br /> > Trial:试用 <br /><br /> > Donate:赠送 <br /><br /> > Used:按量 <br /><br /> > Post:后付费 <br /><br /> > Day:按天 <br /><br /> > Quarter:按季度 <br /><br /> > Semester:按半年 |**Yes**|
| **CreateTime** | int | 创建时间（时间戳） |**Yes**|
| **StartTime** | int | 开始时间（时间戳） |**Yes**|
| **OrderNo** | string | 订单号 |**Yes**|
| **OrderType** | string | 订单类型。枚举值：<br /><br /> > OT_BUY:新购 <br /><br /> > OT_RENEW:续费 <br /><br /> > OT_UPGRADE:升级 <br /><br /> > OT_REFUND:退费 <br /><br /> > OT_DOWNGRADE:降级 <br /><br /> > OT_ADDITIONAL:补单 <br /><br /> > OT_SUSPEND:结算 <br /><br /> > OT_PAYMENT:删除资源回款 <br /><br /> > OT_POSTPAID_PAYMENT:后付费回款 <br /><br /> > OT_RECOVER:删除恢复 <br /><br /> > OT_POSTPAID_RENEW:过期续费回款 |**Yes**|
| **ProjectName** | string | 项目名称 |**Yes**|
| **ResourceId** | string | 资源ID |**Yes**|
| **ResourceType** | string | 产品类型。枚举值：<br /><br /> > uhost:云主机 <br /><br /> > udisk:普通云硬盘 <br /><br /> > udb:云数据库 <br /><br /> > eip:弹性IP <br /><br /> > ufile:对象存储 <br /><br /> > fortress_host:堡垒机 <br /><br /> > ufs:文件存储 <br /><br /> > waf:WEB应用防火墙 <br /><br /> > ues:弹性搜索 <br /><br /> > udisk_ssd:SSD云硬盘 <br /><br /> > rssd:RSSD云硬盘 |**Yes**|
| **ResourceTypeCode** | int | 产品类型代码 |**Yes**|
| **ItemDetails** | array[[*ItemDetail*](#ItemDetail)] | 产品配置 |**Yes**|
| **ResourceExtendInfo** | array[[*ResourceExtendInfo*](#ResourceExtendInfo)] | 资源标识 |**Yes**|
| **ShowHover** | int | 订单支付状态。枚举值：<br /><br />> 0:未支付 <br /><br /> > 1:已支付 |**Yes**|
| **UserEmail** | string | 账户邮箱 |**Yes**|
| **UserName** | string | 账户名 |**Yes**|
| **UserDisplayName** | string | 账户昵称 |**Yes**|
| **Admin** | int | 是否为主账号。枚举值：<br /><br /> > 0:子账号 <br /><br /> > 1:主账号 |**Yes**|

#### ItemDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductName** | string | 产品小类名称 |**Yes**|
| **Value** | string | 产品小类规格 |**Yes**|

#### ResourceExtendInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 资源标识健 |**Yes**|
| **Value** | string | 资源标识值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUBillDetail
&BillingCycle= 2022-01,
&ResourceTypes.0= uhost,
&ResourceTypes.1= udisk,
&ProjectName= Default,
&ResourceIds.0= uhost-bzgf1gh5,
&ResourceIds.1= uhost-gu1xpspa,
&OrderType= OT_RENEW,
&ChargeType= Dynamic,
&ShowZero= 0,
&PaidState= 0,
&Limit= 25,
&Offset= 0
```

### 响应示例
    
```json
{
  "Action": "ListUBillDetailResponse",
  "Items": [
    {
      "Admin": 1,
      "Amount": "4.21",
      "AmountCoupon": "0.00",
      "AmountFree": "0.00",
      "AmountReal": "4.21",
      "AzGroupCName": "北京二",
      "ChargeType": "Dynamic",
      "CreateTime": 1643641241,
      "EndTime": 1643644800,
      "ItemDetails": [
        {
          "ProductName": "主机CPU",
          "Value": "4核"
        },
        {
          "ProductName": "主机内存",
          "Value": "16384MB"
        },
        {
          "ProductName": "GPU_P40",
          "Value": "1颗"
        },
        {
          "ProductName": "SSD云盘（系统盘）",
          "Value": "40GB"
        }
      ],
      "OrderNo": "20220131033108259519838",
      "OrderType": "OT_RENEW",
      "ProjectName": "Default",
      "ResourceExtendInfo": [
        {
          "KeyId": "name",
          "Value": "UHost-hl4"
        },
        {
          "KeyId": "private_ip",
          "Value": "10.25.113.204"
        }
      ],
      "ResourceId": "uhost-bzgf1gh5",
      "ResourceType": "uhost",
      "ResourceTypeCode": 1,
      "ShowHover": 1,
      "StartTime": 1643641200,
      "UserDisplayName": "数据学院",
      "UserEmail": "daseucloud@foxmail.com",
      "UserName": "root"
    },
    {
      "Admin": 1,
      "Amount": "4.21",
      "AmountCoupon": "0.00",
      "AmountFree": "0.00",
      "AmountReal": "4.21",
      "AzGroupCName": "北京二",
      "ChargeType": "Dynamic",
      "CreateTime": 1643641239,
      "EndTime": 1643644800,
      "ItemDetails": [
        {
          "ProductName": "主机CPU",
          "Value": "4核"
        },
        {
          "ProductName": "主机内存",
          "Value": "16384MB"
        },
        {
          "ProductName": "GPU_P40",
          "Value": "1颗"
        },
        {
          "ProductName": "SSD云盘（系统盘）",
          "Value": "40GB"
        }
      ],
      "OrderNo": "20220131032808257245615",
      "OrderType": "OT_RENEW",
      "ProjectName": "Default",
      "ResourceExtendInfo": [
        {
          "KeyId": "name",
          "Value": "UHost-hl2"
        },
        {
          "KeyId": "private_ip",
          "Value": "10.25.98.190"
        }
      ],
      "ResourceId": "uhost-gu1xpspa",
      "ResourceType": "uhost",
      "ResourceTypeCode": 1,
      "ShowHover": 1,
      "StartTime": 1643641200,
      "UserDisplayName": "数据学院",
      "UserEmail": "daseucloud@foxmail.com",
      "UserName": "root"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





