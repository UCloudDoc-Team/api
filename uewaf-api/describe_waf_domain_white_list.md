# 获取域名白名单列表 - DescribeWafDomainWhiteList

## 简介

获取域名白名单列表








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafDomainWhiteList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要获取的白名单的域名 |**Yes**|
| **Limit** | int | 每个请求限制返回数量，等效于page size |**Yes**|
| **Offset** | int | 偏移，等效于 page number |**Yes**|
| **Filter** | string | 想要查找的IP、网段或者IP段，传递数组（CIDRS） |No|
| **Sort** | string | 排序参数，支持"CreateTime", "-CreateTime" |No|
| **Name** | string | 规则名称 |No|
| **Remark** | string | 备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Res** | [*BWInfoRes*](#BWInfoRes) | 白名单返回结果，参考BWInfoRes |**Yes**|

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
| **Geo** | array[string] | 位置信息 |No|
| **Name** | string | 规则名称 |No|
| **Remark** | string | 备注信息 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafDomainWhiteList
&ProjectId=org-xxx
&FullDomain=www.test.com
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeWafDomainWhiteListResponse",
  "Res": {
    "Count": 1,
    "Info": [
      {
        "ActionType": "accept",
        "CIDRS": [
          "1.1.1.1"
        ],
        "CreateTime": "2020-02-27 09:50:10",
        "ExpireTime": 0,
        "ID": 15022,
        "Name": "",
        "Remark": "",
        "SRC": "custom",
        "Source": "",
        "State": 0,
        "Type": ""
      }
    ],
    "Total": 1
  },
  "RetCode": 0
}
```





