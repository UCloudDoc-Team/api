# 查询短链接访问明细列表 - DescribeUSLKRedirectRecords

## 简介

查询短链接访问明细列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUSLKRedirectRecords`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询周期开始时间戳(ms级别) |**Yes**|
| **EndTime** | int | 查询周期结束时间戳(ms级别) |**Yes**|
| **ShortLink** | string | 短链接 |**Yes**|
| **Page** | int | 页码，从0开始，用于分页查找 |No|
| **NumPerPage** | int | 每页个数，用于分页查找，默认20 |No|
| **OrderBy** | string | 根据指定字段排序：默认按短链接访问时间：CreateTime 排序 |No|
| **OrderType** | string | 排序方式。asc-正序 desc-倒序<br /> |No|
| **FuzzySearch** | string | 模糊查询字段值，支持根据生成短链接进行模糊查询。支持字段(ShortLink，场景名称)<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*RedirectRecords*](#RedirectRecords)] | 长链接列表 |No|
| **Total** | int | 数据总量 |No|

#### 数据模型


#### RedirectRecords

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Scenario** | string | 报备场景 |**Yes**|
| **ShortLink** | string | 短链接 |**Yes**|
| **ShortLinkDomain** | string | 短链接域名 |**Yes**|
| **RequestTime** | int | 访问时间戳（ms） |**Yes**|
| **RedirectTime** | int | 重定向时间戳 (ms) |**Yes**|
| **AccountID** | int | 账户ID |**Yes**|
| **ScenarioID** | int | 场景ID |**Yes**|
| **ClientIP** | string | 访问IP |**Yes**|
| **Browser** | string | 访问设备 |**Yes**|
| **Os** | string | 访问操作系统 |**Yes**|
| **ProvinceCode** | string | 访问省份信息 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUSLKRedirectRecords
&Page=3
&Status=4
&ScenarioID=1
&NumPerPage=1
&OrderBy=DsgHFexL
&OrderType=Year
&FuzzySearch=OWfaBIbm
&EndTime=7
```

### 响应示例
    
```json
{
  "Action": "DescribeUSLKRedirectRecordsResponse",
  "Data": [
    {
      "AccountID": 4,
      "CreateTime": 5,
      "DeleteTime": 6,
      "ID": 2,
      "LongLink": "XFnuILTA",
      "Operator": "HmffUPiB",
      "Remark": "SCWOwbzX",
      "Scenario": "rAiOgHDy",
      "ScenarioDesc": "vDaHdwNH",
      "ScenarioID": 7,
      "Status": 8,
      "UpdateTime": 4
    }
  ],
  "Message": "MJwEUtUK",
  "ReqUuid": "lzfwADJg",
  "RetCode": 0,
  "Total": "XaaUFRZf"
}
```





