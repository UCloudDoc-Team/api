# 申请内网虚拟IP - AllocateVIP

## 简介

根据提供信息，申请内网VIP(Virtual IP），多用于高可用程序作为漂移IP。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateVIP)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateVIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |**Yes**|
| **Zone** | string | 可用区 |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **VPCId** | string | 指定vip所属的VPC |**Yes**|
| **SubnetId** | string | 子网id |**Yes**|
| **Ip** | string | 指定ip |No|
| **Count** | int | 申请数量，默认: 1 |No|
| **Name** | string | vip名，默认：VIP |No|
| **Tag** | string | 业务组名称，默认为Default |No|
| **Remark** | string | 备注 |No|
| **BusinessId** | string | 业务组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VIPSet** | array[[*VIPSet*](#VIPSet)] | 申请到的VIP资源相关信息 |No|
| **DataSet** | array[string] | 申请到的VIP地址 |No|

#### 数据模型


#### VIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VIP** | string | 虚拟ip |No|
| **VIPId** | string | 虚拟ip id |No|
| **VPCId** | string | VPC id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateVIP
&Region=cn-bj2
&ProjectId=org-XXXX
&Zone=cn-bj2-04
&VPCId=vnet-XXXXXX
&SubnetId=subnet-XXX
&Ip=ccjyLEtQ
```

### 响应示例
    
```json
{
  "Action": "AllocateVIPResponse",
  "DataSet": [
    "10.25.XX.111"
  ],
  "RetCode": 0,
  "VIPSet": [
    {
      "VIP": "10.25.XX.111",
      "VIPId": "vip-XXXXXX",
      "VPCId": "uvnet-XXXXX"
    }
  ]
}
```





