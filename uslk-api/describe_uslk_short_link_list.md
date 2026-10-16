# 查询短链接列表 - DescribeUSLKShortLinkList

## 简介

查询短链接列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUSLKShortLinkList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Page** | int | 页码，从0开始，用于分页查找 |No|
| **Status** | int | 1: 待生效；2：已生效；3：已失效；4：已删除（预留）；5：已封禁 |No|
| **NumPerPage** | int | 每页个数，用于分页查找，默认20 |No|
| **OrderBy** | string | 根据指定字段排序：默认按创建时间：CreateTime 排序，支持值：CreateTime,StartTime,EndTime |No|
| **OrderType** | string | 排序方式。asc-正序 desc-倒序<br /> |No|
| **FuzzySearch** | string | 模糊查询字段值，支持根据生成短链接进行模糊查询。支持字段(LonkLink,场景名称)<br /> |No|
| **StartTime** | int | 查询周期开始时间戳 |No|
| **EndTime** | int | 查询周期结束时间戳 |No|
| **ShortLink** | string | 短链 |No|
| **ScenarioID** | int | 场景ID |No|
| **LongLinkID** | int | 长链接ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ShortLink*](#ShortLink)] | 短链接列表 |No|

#### 数据模型


#### ShortLink

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Scenario** | string | 报备场景 |**Yes**|
| **ShortLink** | string | 短链接 |**Yes**|
| **ShortLinkDomain** | string | 短链接域名 |**Yes**|
| **StartTime** | int | 短链接开始生效时间戳 |**Yes**|
| **EndTime** | int | 短链接过期时间戳 |**Yes**|
| **LongLinks** | array[string] | 关联长链接列表 |**Yes**|
| **CreateTime** | int | 短链接创建时间 |**Yes**|
| **ID** | int | 短链接ID |**Yes**|
| **ScenarioID** | int | 场景ID |**Yes**|
| **ScenarioDesc** | string | 场景描述 |**Yes**|
| **UpdateTime** | int | 更新时间戳 |**Yes**|
| **DeleteTime** | int | 删除时间戳 |**Yes**|
| **Type** | int | 链接类型-预留：1:普通跳转 3:智能跳转等 |**Yes**|
| **Status** | int | 短链接状态：1: 待生效；2：已生效；3：已失效；4：已删除（预留）；5：已封禁 |**Yes**|
| **Operator** | string | 操作人 |**Yes**|
| **Remark** | string | 操作说明(封禁原因) |**Yes**|
| **ClickCount** | int | 累计访问量 |**Yes**|
| **ClickCountToday** | int | 当日访问量 |**Yes**|
| **UniqueClickCount** | int | 累计独立访问量 |**Yes**|
| **UniqueClickCountToday** | int | 今日独立访问量 |**Yes**|
| **SecondaryLinks** | array[[*SecondaryLinkForQuery*](#SecondaryLinkForQuery)] | 次链接，智能跳转类型才有 |No|

#### SecondaryLinkForQuery

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LongLinkID** | int | 长链接ID |**Yes**|
| **ShortLongMapID** | int | 长短链接映射ID |**Yes**|
| **LongLink** | string | 长链接 |**Yes**|
| **ScenarioID** | int | 场景ID |**Yes**|
| **Scenario** | string | 场景名称 |**Yes**|
| **IsSecondary** | boolean | 是否是次链接 |**Yes**|
| **ProvinceCodes** | string | 省份codes，例如: Hebei,Shandong,多个以逗号分隔 |**Yes**|
| **Oses** | string | 操作系统,例如: Windows,Android,多个以逗号分隔 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUSLKShortLinkList
&Page=6
&Status=1
&NumPerPage=2
&OrderBy=SLIqKgte
&OrderType=Year
&FuzzySearch=ppFVeier
&StartTime=5
&EndTime=8
&ShortLink=tzpklqaj
&ScenarioID=2
&LongLinkID=1
```

### 响应示例
    
```json
{
  "Action": "DescribeUSLKShortLinkListResponse",
  "Data": [
    {
      "ClickCount": 9,
      "ClickCountToday": 8,
      "CreateTime": 1,
      "DeleteTime": 3,
      "EndTime": 6,
      "ID": 6,
      "LongLinks": [
        "QYabiQZS"
      ],
      "Operator": "PDNVFvvA",
      "Remark": "AlbyqCHz",
      "Scenario": "Zivperga",
      "ScenarioDesc": "xssYeRuF",
      "ScenarioID": 7,
      "SecondaryLinks": [
        {
          "Browsers": "bzefHxrA",
          "IsSecondary": false,
          "LongLink": "kIitMuwA",
          "LongLinkID": 5,
          "ProvinceCodes": "wvvpMFyE",
          "Scenario": "TWkLwcdw",
          "ScenarioID": 8,
          "ShortLongMapID": 6
        }
      ],
      "ShortLink": "tmVGHKOv",
      "ShortLinkDomain": "qtBHZKlU",
      "StartTime": 8,
      "Status": 7,
      "Type": 6,
      "UniqueClickCount": 6,
      "UniqueClickCountToday": 5,
      "UpdateTime": 6
    }
  ],
  "Message": "qeqAuPkq",
  "RetCode": 0
}
```





