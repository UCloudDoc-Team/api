# 创建云游戏实例 - CreateUGameInstance

## 简介

创建云游戏实例









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGameInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeCities)获取 |**Yes**|
| **UserId** | string | 客户端用户ID |**Yes**|
| **AppId** | string | 应用的唯一标识ID，和AppVersionId必传其一 |No|
| **AppVersionId** | string | 应用版本的唯一标识ID，和AppId必传其一 |No|
| **Resolution** | string | 游戏分辨率，默认为1080x2160 |No|
| **Refresh** | int | 云手机画面刷新率，即帧率 |No|
| **BitRate** | int | 云手机画面传输码率 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGameId** | string | 云游戏实例唯一标识ID |**Yes**|
| **UPhoneId** | string | 云手机实例的资源ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGameInstance
&ProjectId=TYSiFfzJ
&AppId=zCDjEIWF
&CityId=hzeovCHB
&Resolution=XQeEnkMN
&UserId=dlnLsWxV
&AppVersionId=xljLODLQ
&Refresh=TjxIOxRS
&Bitrate=ExvQODxR
&Refresh=6
&Bitrate=3
```

### 响应示例
    
```json
{
  "Action": "CreateUGameInstanceResponse",
  "Message": "kJygKqaB",
  "RetCode": 0,
  "UGameId": "FiRrJgKx",
  "UPhoneId": "OZQMLFEj"
}
```





