# 获取Cube的额外信息 - GetCubeExtendInfo

## 简介

获取Cube的额外信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCubeExtendInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **CubeIds** | string | id列表以逗号(,)分割 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ExtendInfo** | array[[*CubeExtendInfo*](#CubeExtendInfo)] | CubeExtendInfo |**Yes**|

#### 数据模型


#### CubeExtendInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CubeId** | string | Cube的Id |**Yes**|
| **Name** | string | Cube的名称 |No|
| **Eip** | array[[*EIPSet*](#EIPSet)] | EIPSet |No|
| **Expiration** | int | 资源有效期 |No|
| **Tag** | string | 业务组名称 |No|

#### EIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Bandwidth** | int | EIP带宽值 |No|
| **BandwidthType** | int | 带宽类型0标准普通带宽，1表示共享带宽 |No|
| **CreateTime** | int | EIP创建时间 |No|
| **EIPAddr** | array[[*EIPAddr*](#EIPAddr)] | EIP地址 |No|
| **EIPId** | string | EIPId |No|
| **PayMode** | string | 付费模式，带宽付费或者流量付费 |No|
| **Resource** | string | EIP绑定对象的资源Id |No|
| **Status** | string | EIP状态，表示使用中或者空闲 |No|
| **Weight** | string | EIP权重 |No|

#### EIPAddr

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | IP地址 |No|
| **OperatorName** | string | 线路名称BGP或者internalation |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCubeExtendInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wqWvowms
&CubeIds=MuRksrzy
```

### 响应示例
    
```json
{
  "Action": "GetCubeExtendInfoResponse",
  "ExtendInfo": [
    {
      "CubeId": "WbDqEAaB",
      "Eip": "AgJwuYWw",
      "Name": "SCXnvwzq"
    }
  ],
  "RetCode": 0
}
```





