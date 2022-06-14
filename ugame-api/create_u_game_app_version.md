# 创建云游戏应用版本 - CreateUGameAppVersion

## 简介

创建云游戏应用版本









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGameAppVersion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **GameName** | string | 游戏名称 |**Yes**|
| **Name** | string | 应用版本名称，最大字符长度为255。 |**Yes**|
| **Url** | string | 应用版本相关的Apk文件存放的公网URL地址。 |**Yes**|
| **Adapt** | boolean | 是否适配，默认否 |No|
| **Description** | string | 应用版本描述。 |No|
| **PackageName** | string | 应用包名 |No|
| **MainActivity** | string | 启动应用Activity |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AppVersionId** | string | 应用版本的唯一标识ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGameAppVersion
&ProjectId=tsbVciny
&Name=cETFlxmN
&AppId=UETUYYCX
&URL=MVXZDqhM
&Description=syaNtvFl
&GameName=EymcKdDB
&Adapt=true
&PackageName=HDghLdAx
&MainActivity=mNraffMA
```

### 响应示例
    
```json
{
  "Action": "CreateUGameAppVersionResponse",
  "AppVersionId": "ILEfkeTF",
  "RetCode": 0
}
```





