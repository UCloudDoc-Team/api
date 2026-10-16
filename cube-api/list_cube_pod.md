# 获取容器实例详细列表 - ListCubePod

## 简介

获取容器实例详细列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCubePod`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **Group** | string | 容器实例组 |No|
| **VPCId** | string | 容器实例所属VPC |No|
| **SubnetId** | string | 容器实例所属子网 |No|
| **DeploymentId** | string | 容器实例所属Deployment |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Pods** | array[string] | 容器实例yaml列表，以base64编码 |**Yes**|
| **TotalCount** | int | 容器实例总数 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCubePod
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=oxuahZUg
&Offset=6
&Limit=5
&Group=jpGujtVx
&VPCId=ILteIdvJ
&SubnetId=bAIjEiDc
&ChargeType=akJeVJWG
&DeploymentId=MltvETTi
```

### 响应示例
    
```json
{
  "Action": "ListCubePodResponse",
  "Pods": [
    "AIfFhuuU"
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





