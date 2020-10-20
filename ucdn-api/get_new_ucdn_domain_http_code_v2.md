# 获取域名详细状态码监控 - GetNewUcdnDomainHttpCodeV2

## 简介

获取域名详细状态码监控

?> 详细状态码监控仅返回有数量的详细状态码，若无数量则不返回。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnDomainHttpCodeV2)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnDomainHttpCodeV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Type** | int | 时间粒度（0表示按照5分钟粒度，1表示按照1小时粒度，2表示按照一天粒度，3表示按照一分钟粒度） |**Yes**|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。 |**Yes**|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。 |**Yes**|
| **DomainId.N** | string | 域名id，创建域名时生成的id。默认全部域名 |No|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外，只支持国内 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HttpCodeV2Detail** | array[[*HttpCodeV2Detail*](#HttpCodeV2Detail)] | 状态码详情 |No|

#### 数据模型


#### HttpCodeV2Detail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | 时间 |No|
| **Total** | int | 当前分组的总状态码数 |No|
| **Http100** | int | http100数量 |No|
| **Http101** | int | http101数量 |No|
| **Http102** | int | http102数量 |No|
| **Http200** | int | http200数量 |No|
| **Http201** | int | http201数量 |No|
| **Http202** | int | http202数量 |No|
| **Http203** | int | http203数量 |No|
| **Http204** | int | http204数量 |No|
| **Http205** | int | http205数量 |No|
| **Http206** | int | http206数量 |No|
| **Http207** | int | http207数量 |No|
| **Http300** | int | http300数量 |No|
| **Http301** | int | http301数量 |No|
| **Http302** | int | http302数量 |No|
| **Http303** | int | http303数量 |No|
| **Http304** | int | http304数量 |No|
| **Http305** | int | http305数量 |No|
| **Http306** | int | http306数量 |No|
| **Http307** | int | http307数量 |No|
| **Http400** | int | http400数量 |No|
| **Http401** | int | http401数量 |No|
| **Http402** | int | http402数量 |No|
| **Http403** | int | http403数量 |No|
| **Http404** | int | http404数量 |No|
| **Http405** | int | http405数量 |No|
| **Http406** | int | http406数量 |No|
| **Http407** | int | http407数量 |No|
| **Http408** | int | http408数量 |No|
| **Http409** | int | http409数量 |No|
| **Http410** | int | http410数量 |No|
| **Http411** | int | http411数量 |No|
| **Http412** | int | http412数量 |No|
| **Http413** | int | http413数量 |No|
| **Http414** | int | http414数量 |No|
| **Http415** | int | http415数量 |No|
| **Http416** | int | http416数量 |No|
| **Http417** | int | http417数量 |No|
| **Http418** | int | http418数量 |No|
| **Http421** | int | http421数量 |No|
| **Http422** | int | http422数量 |No|
| **Http423** | int | http423数量 |No|
| **Http424** | int | http424数量 |No|
| **Http425** | int | http425数量 |No|
| **Http426** | int | http426数量 |No|
| **Http449** | int | http449数量 |No|
| **Http451** | int | http451数量 |No|
| **Http500** | int | http500数量 |No|
| **Http501** | int | http501数量 |No|
| **Http502** | int | http502数量 |No|
| **Http503** | int | http503数量 |No|
| **Http504** | int | http504数量 |No|
| **Http505** | int | http505数量 |No|
| **Http506** | int | http506数量 |No|
| **Http507** | int | http507数量 |No|
| **Http509** | int | http509数量 |No|
| **Http510** | int | http510数量 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnDomainHttpCodeV2
&ProjectId=wBkjkOLu
&Type=2
&DomainId.n=www.ucloud.cn
&Areacode=cn
&BeginTime=8
&EndTime=8
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnDomainHttpCodeV2Response",
  "HttpCodeV2Detail": [
    {
      "Http200": 2137102581,
      "Http206": 92972,
      "Http302": 5,
      "Http304": 931756,
      "Http404": 230669,
      "Http412": 305,
      "Http416": 74,
      "Http500": 160,
      "Time": 1558443000
    }
  ],
  "RetCode": 0
}
```





