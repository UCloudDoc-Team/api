# 获取域名黑名单列表 - DescribeWafDomainBlackList

## 简介

获取域名黑名单列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafDomainBlackList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **FullDomain** | string | 要查询的域名 |**Yes**|
| **Limit** | int | 每页数量限制(等效page size) |**Yes**|
| **Offset** | int | 页面偏移(等效page number) |**Yes**|
| **Filter** | string | 想要查找的IP、网段或者IP段，传递数组（CIDRS） |No|
| **Sort** | string | 排序参数，支持"ExpireTime", "-ExpireTime", "CreateTime", "-CreateTime" |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Res** | [*BWInfoRes*](#BWInfoRes) | 黑名单返回结果，参考BWInfoRes |No|

#### 数据模型


#### BWInfoRes

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 总数 |No|
| **Count** | int | 返回数量 |No|
| **Info** | array[[*BWInfo*](#BWInfo)] | 详情列表，参考BWInfo |No|

#### BWInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | int | 黑名单/白名单规则ID |No|
| **Type** | string | 类型 |No|
| **Source** | string | 加入方式(黑) |No|
| **CIDRS** | array[string] | IP列表 |No|
| **CreateTime** | string | 加入时间 |No|
| **ExpireTime** | int | 过期时间 |No|
| **State** | int | 状态 |No|
| **SRC** | string | 加入方式(白) |No|
| **Name** | string | 规则名称 |No|
| **Remark** | string | 备注信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
&Offset=0
&Limit=10
&Remark=test
```

### 响应示例
    
```json
{
  "Action": "DescribeWafDomainBlackListResponse",
  "Res": {
    "Count": 3,
    "Info": [
      {
        "ActionType": "forbidden",
        "CIDRS": [
          "1.2.3.4"
        ],
        "CreateTime": "2020-03-26 11:21:03",
        "ExpireTime": 1585193463,
        "ID": 251276,
        "Name": "",
        "Remark": "",
        "SRC": "",
        "Source": "custom",
        "State": 0,
        "Type": "custom"
      },
      {
        "ActionType": "forbidden",
        "CIDRS": [
          "2.2.2.2-2.2.2.10"
        ],
        "CreateTime": "2020-03-28 01:59:05",
        "ExpireTime": 1585332545,
        "ID": 252062,
        "Name": "",
        "Remark": "",
        "SRC": "",
        "Source": "custom",
        "State": 0,
        "Type": "custom"
      },
      {
        "ActionType": "forbidden",
        "CIDRS": [
          "2.2.2.2"
        ],
        "CreateTime": "2020-04-03 10:03:39",
        "ExpireTime": 1585880019,
        "ID": 252731,
        "Name": "",
        "Remark": "",
        "SRC": "",
        "Source": "custom",
        "State": 0,
        "Type": "custom"
      }
    ],
    "Total": 3
  },
  "RetCode": 0
}
```





