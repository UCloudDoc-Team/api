# 删除UK8S日志采集配置 - DeleteUK8SULSConfig

## 简介

删除指定UK8S集群的日志采集规则。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteUK8SULSConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **Zone** | string | 可用区。参见可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。请参考GetProjectList接口。 |No|
| **ClusterId** | string | 要操作的 UK8S 集群的 ID。 |**Yes**|
| **Name** | string | 要删除的日志的采集规则的名称。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteUK8SULSConfig
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=nHcJZlAa
&ClusterId=zncnSZgi
&TopicId=xhTUeszG
```

### 响应示例
    
```json
{
  "Action": "DeleteUK8SULSConfigResponse",
  "RetCode": 0
}
```





