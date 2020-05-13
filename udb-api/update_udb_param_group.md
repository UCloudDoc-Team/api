# 更新配置 - UpdateUDBParamGroup

## 简介

更新UDB配置参数项





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUDBParamGroup)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUDBParamGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **GroupId** | int | 配置参数组id，使用DescribeUDBParamGroup获得 |**Yes**|
| **Key** | string | 参数名称（与Value配合使用） |No|
| **Value** | string | 参数值（与Key配合使用） |No|
| **Name** | string | 配置文件的名字，不传时认为不修改名字，传了则不能为空 |No|
| **Description** | string | 配置文件的描述，不传时认为不修改 |No|
| **RegionFlag** | boolean | 该配置文件是否是地域级别配置文件，<br />默认是false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUDBParamGroup     
&Region=cn-bj2
&Zone=cn-bj2-04
&GroupId=2
&Key=back_log
&Value=2000
&Name=CJCMVDSu
&Description=WkHCyoXe
&RegionFlag=Wggcb
```

### 响应示例
    
```json
{
  "Action": "UpdateUDBParamGroupResponse",
  "RetCode": 0
}
```





