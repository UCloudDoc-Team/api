# 删除Node节点 - DelUK8SClusterNodeV2

## 简介

删除集群中的Node节点，删除前务必先将其中的Pod驱逐。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DelUK8SClusterNodeV2`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist)<br /> |**Yes**|
| **ClusterId** | string | UK8S集群ID。 可从UK8S控制台获取。<br /> |**Yes**|
| **NodeId** | string | Node在UK8S处的唯一标示，如uk8s-reewqe5-sdasadsda。**非云主机或物理云主机资源Id** |**Yes**|
| **ReleaseDataUDisk** | boolean | 删除节点时是否释放数据盘。 枚举值[true:释放，false: 不释放]，默认为true。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DelUK8SClusterNodeV2
&ProjectId=Mnrabzut
&Region=wvsgqKEY
&ClusterId=IJeDHQLE
&Name=cXwAudcP
&NodeId=phbIHHoH
&ReleaseDataUDisk=false
```

### 响应示例
    
```json
{
  "Action": "DelUK8SClusterNodeV2Response",
  "Message": "MNTqlFPZ",
  "RetCode": 0
}
```





