# 查询主备Redis所有配置文件 - DescribeURedisConfig

## 简介

查询主备Redis所有配置文件






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeURedisConfig)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURedisConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **RegionFlag** | boolean | 是否是跨机房URedis(默认false) |**Yes**|
| **Version** | string | Redis版本号 |No|
| **ConfigId** | string | 配置文件ID |No|
| **Offset** | int | 页显示的起始偏移, 默认值为0 |No|
| **Limit** | int | 页显示的条目数, 默认值为10 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 根据过滤条件得到的总数 |No|
| **DataSet** | array[[*URedisConfigSet*](#URedisConfigSet)] | 配置文件列表 参见 URedisConfigSet |No|

#### 数据模型


#### URedisConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | Zone |No|
| **ConfigId** | string | 配置ID |No|
| **Name** | string | 配置名称 |No|
| **Description** | string | 配置描述 |No|
| **Version** | string | 配置对应的Redis版本 |No|
| **IsModify** | string | 置是否可以修改 |No|
| **State** | string | 配置所处的状态 |No|
| **CreateTime** | int | 创建时间 (UNIX时间戳) |No|
| **ModifyTime** | int | 修改时间 (UNIX时间戳) |No|
| **RegionFlag** | boolean | 是否是跨机房URedis(默认false) |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURedisConfig
&Region=cn-zj
&Zone=cn-zj-01
&ConfigId=EmTNpurL
&Offset=8
&Limit=2
&ProjectId=VuPSDiad
&Version=qyhfGmaZ
```

### 响应示例
    
```json
{
  "Action": "DescribeURedisConfigResponse",
  "DataSet": [
    {
      "ConfigId": "03f58ca9-b64d-4bdd-abc7-c6b9a46fd801",
      "CreateTime": 1425458755,
      "Description": "default-config",
      "IsModify": "Unmodifiable",
      "ModifyTime": 1425458755,
      "Name": "redis-3.0",
      "RegionFlag": false,
      "State": "Usable",
      "Version": "3.0",
      "Zone": "......"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





