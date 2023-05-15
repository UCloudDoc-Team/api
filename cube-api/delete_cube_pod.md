# 删除容器实例 - DeleteCubePod

## 简介

删除容器实例









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteCubePod`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Uid** | string | 要删除的容器实例UID，若填写了CubeId则可忽略 |No|
| **CubeId** | string | 要删除的容器实例ID，若填写了Uid则可忽略 |No|
| **ReleaseEIP** | string | 要释放的EIP，如果容器实例绑定了EIP则可以填写，会将EIP一并释放。否则EIP会被保留。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteCubePod
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=vdzyLCSu
&CubeId=UBJUunSi
&Uid=jjpjKtPa
&ReleaseEIP=padxhAqe
```

### 响应示例
    
```json
{
  "Action": "DeleteCubePodResponse",
  "RetCode": 0
}
```





