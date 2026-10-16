# 删除云手机服务器 - DeleteUPhoneServer

## 简介

删除云手机服务器。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteUPhoneServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ServerId** | string | 云手机服务器的实例ID 可通过 [DescribeUPhoneServer]()获取 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ReleaseEIP** | boolean | 删除云手机服务器时是否释放绑定的EIP。默认为false。	 |No|
| **ReleaseUDisk** | boolean | 删除云手机服务器时是否同时删除挂载的数据盘。默认为false。	 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteUPhoneServer
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cDHOPDfK
&ServerId=IcVYrXkw
&ReleaseEIP=lEPwWFds
&ReleaseUDisk=JntZZKtA
&ReleaseEIP=false
&ReleaseUDisk=true
&CityId=gbudlQkB
```

### 响应示例
    
```json
{
  "Action": "DeleteUPhoneServerResponse",
  "JobId": "rIDyjToi",
  "Message": "tCitElOp",
  "RetCode": 0
}
```





