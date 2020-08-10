# 批量获取加速域名配置 - GetUcdnDomainConfig

## 简介

批量获取加速域名配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUcdnDomainConfig)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUcdnDomainConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 数据偏移量，默认0，非负整数 |No|
| **Limit** | int | 返回数据长度， 默认全部，非负整数 |No|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认获取账号下的所有域名信息,n为自然数,从DomainId.0开始。 |No|
| **ChannelType** | string | 产品类型ucdn，可不填，默认为ucdn |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DomainList** | array[[*DomainConfigInfo*](#DomainConfigInfo)] | 获取的域名信息，具体参考下面DomainConfig |**Yes**|

#### 数据模型


#### DomainConfigInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaCode** | string | 查询带宽区域 cn代表国内 abroad代表海外 all表示全部区域 |**Yes**|
| **CdnType** | string | 加速域名的业务类型，web代表网站，stream代表视频 ，download 代表下载 |**Yes**|
| **Status** | string | 创建的加速域名的当前的状态。check代表审核中，checkSuccess代表审核通过，checkFail代表审核失败，enable代表加速中，disable代表停止加速，delete代表删除加速<br />enableing代表正在开启加速，disableing代表正在停止加速中，deleteing代表删除中 |**Yes**|
| **Cname** | string | cdn域名。创建加速域名生成的cdn域名，用于设置CNAME记录 |**Yes**|
| **CreateTime** | int | 域名创建的时间。格式：时间戳 |**Yes**|
| **TestUrl** | string | 测试url。用于域名创建加速时的测试 |**Yes**|
| **HttpsStatusCn** | string | 国内https状态 enableing-开启中 fail-开启失败 enable-启用 disable-未启用 |**Yes**|
| **HttpsStatusAbroad** | string | 国外https状态 enableing-开启中  fail-开启失败 enable-启用 disable-未启用 |**Yes**|
| **CertNameCn** | string | 国内证书名称 |**Yes**|
| **CertNameAbroad** | string | 国外证书名称 |**Yes**|
| **Tag** | string | 业务组：Default |**Yes**|
| **DomainId** | string | 域名Id |No|
| **Domain** | string | 域名 |No|
| **OriginConf** | [*OriginConf*](#OriginConf) | 源站配置 |No|
| **AccessControlConf** | [*AccessAllConfig*](#AccessAllConfig) | 访问控制配置 |No|
| **CacheConf** | [*CacheAllConfig*](#CacheAllConfig) | 缓存配置 |No|
| **AdvancedConf** | [*AdvancedConf*](#AdvancedConf) | 高级配置 |No|

#### OriginConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OriginIpList** | array[string] | 源站ip即cdn服务器回源访问的ip地址。多个源站ip，可以这样表述，如：["1.1.1.1","2.2.2.2"] |No|
| **OriginHost** | string | 回源Http请求头部Host，默认是加速域名 |No|
| **OriginPort** | int | 回源端口 |No|
| **BackupOriginEnable** | boolean | 1如果为false表示BackupOriginIp为空，表示没有备份源站，忽略BackupOriginIp，BackupOriginHost字段<br />2如果为true表示BackupOriginIp.n必须至少有一个备份源站地址<br /> |No|
| **BackupOriginIpList** | array[string] | 备份源站ip即cdn服务器回源访问的ip地址。多个源站ip，可以这样表述，如：["1.1.1.1","2.2.2.2"] |No|
| **BackupOriginHost** | string | 备份回源Http请求头部Host，默认是加速域名 |No|
| **OriginErrorCode** | string | 主源响应的回源错误码（如：404\|500），默认空字符串 |No|
| **OriginErrorNum** | int | 回主源的回源失败数，默认1 |No|
| **OriginProtocol** | string | 源站协议http，http\|https   默认http |No|
| **OriginFollow301** | int | 跟随301跳转  0=不跟随 1=跟随 |No|

#### AccessAllConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IpBlackList** | array[string] | ip黑名单列表 ["1.1.1.1","2.2.2.2"] |No|
| **ReferConf** | array[[*ReferConf*](#ReferConf)] | Refer配置,参考ReferConf结构 |No|

#### CacheAllConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CacheHost** | string | 缓存Host，不同的域名可以配置为同一个CacheHost来实现缓存共享，默认为加速域名 |No|
| **CacheList** | array[[*CacheConf*](#CacheConf)] | 缓存配置列表，参见CacheConf |No|
| **HttpCodeCacheList** | array[[*CacheConf*](#CacheConf)] | 状态码缓存配置列表，参见CacheConf |No|
| **CacheKeyList** | array[[*CacheKeyInfo*](#CacheKeyInfo)] | 忽略参数缓存配置列表，参见CacheKeyInfo |No|

#### AdvancedConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **HttpClientHeader** | array[string] | 客户端响应http头列表 |No|
| **HttpOriginHeader** | array[string] | 源站http头列表 |No|
| **Http2Https** | boolean | http转https回源 true是，false否 |No|

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

#### CacheKeyInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ignore** | boolean | 是否忽略 |No|
| **PathPattern** | string | 路径模式，支持正则 |No|
| **QueryString** | string | 自定义变量,以$符号开头，多个变量用加号(+)连接，$querystring表示所有变量 |No|

#### ReferConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ReferType** | int | 0白名单，1黑名单 |No|
| **NullRefer** | int | ReferType为白名单时，(删除)NullRefer为0代表不允许NULL refer访问，为1代表允许Null refer访问 |No|
| **ReferList** | array[string] | Refer列表，支持正则表达式 |No|

## 示例

### 请求示例
    
```
http://api.spark.ucloud.cn/?Action= GetUcdnDomainConfig
& DomainId.0=domain-0331qd
&ChannelType=sdVTSYmK
```

### 响应示例
    
```json
{
  "Action": " GetUcdnDomainConfigResponse",
  "DomainList": [
    {
      "AccessConf": {
        "IpBlackList": [
          "2.2.2.2",
          "3.3.3.3"
        ],
        "ReferConf": {
          "NullRefer": 0,
          "ReferList": [
            "www.baidu.com",
            "www.ucloud.com"
          ],
          "ReferType": 0
        }
      },
      "AdvancedConf": {
        "Http2Https": true,
        "HttpClientHeader": [
          "Access-Control-Allow-Origin:*",
          "Access-Control-Request-Method:GET"
        ],
        "HttpOriginHeader": [
          "Access-Control-Allow-Origin:*",
          "Access-Control-Request-Method:GET"
        ]
      },
      "AreaCode": "cn",
      "CacheConf": {
        "CacheHost": "share.ucloud.cn",
        "CacheList": [
          {
            "CacheBehavior": true,
            "CacheTTL": 12,
            "CacheUnit": "hour",
            "Description": "网站首页",
            "FollowOriginRule": false,
            "IgnoreQueryString": true,
            "PathPattern": "/"
          },
          {
            "CacheBehavior": true,
            "CacheTTL": 12,
            "CacheUnit": "hour",
            "Description": "所有文件",
            "FollowOriginRule": false,
            "IgnoreQueryString": true,
            "PathPattern": "/*.*"
          }
        ]
      },
      "CdnType": "web",
      "CertName": "ucloud_2019",
      "Cname": "9sqlhpr2.cdn.ucloud.cn",
      "CreateTime": 1392974921,
      "Domain": "abc.ucloud.cn",
      "DomainId": "domain-0331qd",
      "HttpsStatusAbroad": "enable",
      "HttpsStatusCn": "enable",
      "OriginConf": {
        "OriginFollow301": 0,
        "OriginHost": "www.xx.com",
        "OriginIpList": [
          "1.1.1.1",
          "2.2.2.2"
        ],
        "OriginPort": 80,
        "OriginProtocol": "http"
      },
      "Status": "enable",
      "Tag": "Default",
      "TestUrl": "http://static.ucloud.cn/logogg.jpg"
    }
  ],
  "RetCode": 0
}
```





