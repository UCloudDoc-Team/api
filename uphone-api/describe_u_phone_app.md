# 获取应用列表 - DescribeUPhoneApp

## 简介

获取应用列表。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **AppIds.N** | string | 数组】应用的唯一标识 ID，调用方式举例：AppIds.0=希望获取应用信息的应用 1，AppIds.1=应用 2。 如果不传入，则返回当前 城市 所有符合条件的应用列表。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | AppInstance总数 |**Yes**|
| **Apps** | array[[*AppInstance*](#AppInstance)] | 云手机应用实例列表，每项参数可见数据模型 [AppInstance](#appInstance) |No|

#### 数据模型


#### AppInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 应用的唯一标识ID |**Yes**|
| **AppName** | string | 应用名称。 |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **Description** | string | 应用描述。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneApp
&Region=cn-zj
&ProjectId=UeiwEyWi
&AppId=dCDfLZSj
&AppName=rnWIlBMe
&Description=IjThxNts
&Offset=6
&Limit=6
&Type=xKfMzOnT
&BizType=lKsfdQWI
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneAppResponse",
  "AppId": "BhDekMQq",
  "Apps": [
    {
      "AppId": "ykLjSpyv",
      "AppName": "YUvzeMgY",
      "CreateTime": "VigHFCjR",
      "Description": "eutXumrO"
    }
  ],
  "Message": "rdSsKXxN",
  "RetCode": 0
}
```





