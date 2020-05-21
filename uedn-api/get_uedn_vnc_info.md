# 获取vnc登录信息 - GetUEdnVncInfo

## 简介

获取vnc登录信息








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEdnVncInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **NodeId** | string | 节点ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeId** | string | 节点ID |**Yes**|
| **VncIP** | string | Vnc登录IP |**Yes**|
| **VncPort** | int | Vnc登录端口 |**Yes**|
| **VncPassword** | string | Vnc 登录密码 |**Yes**|
| **VncToken** | string | Vnc token，一次访问有效 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEdnVncInfo
&ProjectId=VkGeNeZM
&NodeId=Hbvirfhj
```

### 响应示例
    
```json
{
  "Action": "GetUEdnVncInfoResponse",
  "NodeId": "UIASOFRM",
  "RetCode": 0,
  "VncIP": "VZaZkFTg",
  "VncPassword": "CLIMiIit",
  "VncPort": 3,
  "VncToken": "kacNlSjP"
}
```





