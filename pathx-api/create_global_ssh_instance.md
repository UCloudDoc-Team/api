# 创建GlobalSSH实例 - CreateGlobalSSHInstance

## 简介

创建GlobalSSH实例



!> 单一项目下入门版本的GlobalSSH实例有配额限制。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateGlobalSSHInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateGlobalSSHInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Area** | string | 填写支持SSH访问IP的地区名称，如“洛杉矶”，“新加坡”，“香港”，“东京”，“华盛顿”，“法兰克福”，“首尔”。Area和AreaCode两者必填一个 |**Yes**|
| **TargetIP** | string | 被SSH访问的源站IP，仅支持IPv4地址。 |**Yes**|
| **Port** | int | 源站服务器监听的SSH端口，可取范围[1-65535]，不能使用80，443,  65123端口。如果InstanceType=Free，取值范围缩小为[22,3389],linux系统选择22，windows系统自动选3389。 |**Yes**|
| **AreaCode** | string | AreaCode, 区域航空港国际通用代码。Area和AreaCode两者必填一个 |**Yes**|
| **Remark** | string | 备注信息 |No|
| **ChargeType** | string | 支付方式，如按月：Month、 按年：Year、按时：Dynamic |No|
| **Quantity** | int | 购买数量<br />按月购买至月底请传0 |No|
| **InstanceType** | string | 枚举值：["Ultimate","Enterprise","Basic","Primary"], 分别代表旗舰版，企业版，基础版，入门版 |No|
| **BandwidthPackage** | int | Ultimate版本带宽包大小,枚举值：[0,20,40]。单位MB |No|
| **ForwardRegion** | string | InstanceType等于Basic时可以在["cn-bj2","cn-sh2","cn-gd"]中选择1个作为转发机房，其他付费版默认配置三个转发机房 |No|
| **CouponId** | string | 使用代金券可冲抵部分费用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceId** | string | 实例ID，资源唯一标识 |**Yes**|
| **AcceleratingDomain** | string | 加速域名，访问该域名可就近接入 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateGlobalSSHInstance
&ProjectId=org-xxxx
&Remark=备注
&Area=洛杉矶
&TargetIP=1.1.2.2
&Port=22
&CouponId=coupon-123
&ChargeType=Year
&Quantity=1
&AreaCode=LAX
&InstanceType=Basic
&BandwidthPackage=5
&ForwardRegion=UKclgoRu
```

### 响应示例
    
```json
{
  "AcceleratingDomain": "1.1.2.2.ipssh.net",
  "Action": "CreateGlobalSSHInstanceResponse",
  "InstanceId": "uga-xxxx",
  "Message": "",
  "RetCode": 0
}
```





