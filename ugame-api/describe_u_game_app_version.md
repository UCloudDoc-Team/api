# 获取应用版本列表 - DescribeUGameAppVersion

## 简介

获取应用版本列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUGameAppVersion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **AppVersionIds.N** | string | 【数组】应用版本的唯一标识 ID，调用方式举例：AppVersionIds.0=希望获取应用版本信息的应用版本 1，AppVersionIds.1=应用版本 2。 如果不传入，则返回当前 城市 所有符合条件的应用版本列表。 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | AppVersionInstance总数 |**Yes**|
| **AppVersions** | array[[*AppVersionInstance*](#AppVersionInstance)] | 云游戏应用版本实例列表，每项参数可见数据模型 [AppVersionInstance](#AppVersionInstance) |**Yes**|

#### 数据模型


#### AppVersionInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppVersionId** | string | 应用版本的唯一标识ID |**Yes**|
| **AppVersionName** | string | 应用版本名。 |**Yes**|
| **GameName** | string | 游戏名称。 |**Yes**|
| **OnlineState** | string | 上线状态：<br />UnAdaptive（未适配）<br />Adapting（适配中）<br />StayOnline（待上线）<br />Online（已上线）<br />Offline（已下线） |**Yes**|
| **Url** | string | 应用版本相关的Apk文件存放的公网URL地址。 |**Yes**|
| **AllocatedCount** | int | 已分配实例数量 |**Yes**|
| **CreateTime** | int | 创建时间，格式为Unix时间戳。 |**Yes**|
| **ModifyTime** | int | 修改时间，格式为Unix时间戳。 |**Yes**|
| **Type** | string | 类型：<br />PUBLIC（共有）<br />PRIVATE（私有） |**Yes**|
| **PackageName** | string | 包名 |**Yes**|
| **MainActivity** | string | 应用启动Activity |**Yes**|
| **Description** | string | 应用版本描述。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUGameAppVersion
&ProjectId=HvYLydog
&AppVersionIds.N=fQWyBWNW
&AppId=OEjEZDzF
&Limit=8
&Offset=9
```

### 响应示例
    
```json
{
  "Action": "DescribeUGameAppVersionResponse",
  "AppVersions": [
    {
      "AppId": "GLzLepWS",
      "AppVersionId": "KqrOylod",
      "AppVersionName": "azExjSjC",
      "CreateTime": 4,
      "Description": "UBecORuC",
      "ModifyTime": 5,
      "PackageName": "CsOweqkw",
      "URL": "fzAyqIQY"
    }
  ],
  "Message": "kUaqtsOu",
  "RetCode": 0,
  "TotalCount": 3
}
```





