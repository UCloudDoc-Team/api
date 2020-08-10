# 批量获取加速域名配置 - BatchDescribeNewUcdnDomain

## 简介

批量获取加速域名配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BatchDescribeNewUcdnDomain)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BatchDescribeNewUcdnDomain`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量，默认0，非负整数 |No|
| **Limit** | int | 返回数据长度，如果制定了Offset，则默认20，否则默认全部，非负整数 |No|
| **DomainId.N** | string | 域名id，创建域名时生成的资源id，默认获取账号下的所有域名信息，n为自然数 |No|
| **ChannelType** | string | 渠道ucdn、ufile、uvideo |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的域名个数 |No|
| **MaxDomainNum** | int | 最大域名数量，默认20 |No|
| **ChargeType** | int | 当前计费方式，10-流量付费 20-带宽日峰值 30-月95计费，31-月日均峰值， 32-月第四峰值 33-日均峰值之和 34- 日95再取平均 40-未选择计费方式 |No|
| **LastChargeType** | int | 表示最后一次切换的计费方式，10=流量付费 20=带宽日峰值  30=按月后付费  40=未选择计费方式 |No|
| **Arrearage** | array[string] | 标识欠费的数组，数组含有下列元素值， 1=国内流量有欠费 2=国外流量有欠费  3=国内带宽有欠费 4=国外带宽有欠费 |No|
| **Vip** | string | vip标示，yes-是  no-否 |No|
| **DomainSet** | array[[*DomainInfo*](#DomainInfo)] | 域名信息列表，参见DomainInfo |No|

#### 数据模型


#### DomainInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OriginIp** | array[string] | 源站ip即cdn服务器回源访问的ip地址。支持多个源站ip，多个源站ip，可表述为如：[1.1.1.1,2.2.2.2] |**Yes**|
| **TestUrl** | string | 测试url，用于域名创建加速时的测试 |**Yes**|
| **CdnType** | string | 加速域名的业务类型，web代表网站，stream代表视频，download代表下载。 |**Yes**|
| **CacheConf** | array[[*CacheConf*](#CacheConf)] | 缓存配置规则列表 |**Yes**|
| **AreaCode** | string | 查询带宽区域 cn代表国内 abroad代表海外 不填默认为全部区域 |No|
| **OriginHost** | string | 回源Http请求头部Host，默认是加速域名 |No|
| **OriginPort** | int | 回源端口 |No|
| **CdnProtocol** | string | 加速类型http,http\|https |No|
| **OriginProtocol** | string | 源站协议http，http\|https   默认http |No|
| **CertName** | string | 证书名称 |No|
| **Tag** | string | 业务组，默认为Default |No|
| **CacheHost** | string | 缓存Host，不同的域名可以配置为同一个CacheHost来实现缓存共享，默认为加速域名 |No|
| **ReferType** | int | 0白名单，1黑名单 |No|
| **NullRefer** | boolean | ReferType为白名单时，NullRefer为false代表不允许NULL refer访问，为true代表允许Null refer访问 |No|
| **ReferList** | array[string] | Refer列表，支持正则表达式 |No|
| **Domain** | string | 域名，用户创建加速的域名 |No|
| **DomainId** | string | 域名id，创建域名时生成的id |No|
| **Status** | string | 创建的加速域名的当前的状态。check代表审核中，checkSuccess代表审核通过，checkFail代表审核失败，enable代表加速中，disable代表停止加速，delete代表删除加速 enableing代表正在开启加速，disableing代表正在停止加速中，deleteing代表删除中 |No|
| **Cname** | string | cdn域名。创建加速域名生成的cdn域名，用于设置CNAME记录 |No|
| **CreateTime** | int | 域名创建的时间。格式：时间戳 |No|
| **ValidTime** | int | 开始分配Cname时间。格式：时间戳 |No|
| **AccessConf** | [*AccessConf*](#AccessConf) | 访问控制 |No|
| **ReferStatus** | boolean | refer配置开关，true打开，false关闭 |No|
| **HttpsStatusCn** | string | 国内https状态 enableing-开启中 fail-开启失败 enable-启用 disable-未启用 |No|
| **HttpsStatusAbroad** | string | 国外https状态 enableing-开启中  fail-开启失败 enable-启用 disable-未启用 |No|

#### CacheConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **HttpCodePattern** | string | 状态码模式，非200，206状态码，多个状态码用竖线(\|)分隔，该属性仅仅在状态码缓存配置列表中返回 |No|
| **PathPattern** | string | 路径模式，支持正则 |No|
| **Description** | string | 缓存规则描述 |No|
| **CacheTTL** | int | 缓存时间 |No|
| **CacheUnit** | string | 缓存时间的单位。sec（秒），min（分钟），hour（小时），day（天）。上限1年。 |No|
| **CacheBehavior** | boolean | 是否缓存，true为缓存，flase为不缓存。为flase的情况下，CacheTTL和CacheUnit强制不生效 |No|
| **FollowOriginRule** | boolean | 是否优先遵循源站头部缓存策略，false为不优先遵循源站，true为优先遵循源站缓存头部。默认为0 |No|

#### AccessConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IpBlacklist** | string | 多个ip用逗号隔开 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BatchDescribeNewUcdnDomain
&ProjectId=ZQiDGIbu
&Offset=0
&Limit=20
&DomainId.0=ucdn-xxxx
&ChannelType=ucdn
```

### 响应示例
    
```json
{
  "Action": "BatchDescribeNewUcdnDomainResponse",
  "RetCode": 0
}
```





