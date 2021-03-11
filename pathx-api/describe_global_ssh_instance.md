# 获取GlobalSSH实例列表 - DescribeGlobalSSHInstance

## 简介

获取GlobalSSH实例列表（传实例ID获取单个实例信息，不传获取项目下全部实例）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeGlobalSSHInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeGlobalSSHInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 实例ID，资源唯一标识 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **InstanceSet** | array[[*GlobalSSHInfo*](#GlobalSSHInfo)] | GlobalSSH实例列表，实例的属性参考GlobalSSHInfo模型 |No|

#### 数据模型


#### GlobalSSHInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **InstanceId** | string | 实例ID，资源唯一标识 |**Yes**|
| **InstanceType** | string | 枚举值：["Enterprise","Basic","Free","Welfare"], 分别代表企业版，基础版本，免费版本，较早的公测免费版 |**Yes**|
| **AcceleratingDomain** | string | GlobalSSH分配的加速域名。 |**Yes**|
| **Area** | string | 被SSH访问的IP所在地区 |**Yes**|
| **TargetIP** | string | 被SSH访问的源站 IPv4地址。 |**Yes**|
| **Remark** | string | 备注信息 |**Yes**|
| **Port** | int | 源站服务器监听的SSH端口，windows系统为RDP端口 |**Yes**|
| **GlobalSSHPort** | int | InstanceType等于Free时，由系统自动分配，不等于源站Port值。InstanceType不等于Free时，与源站Port值相同。 |**Yes**|
| **ChargeType** | string | 支付周期，如Month,Year,Dynamic等 |**Yes**|
| **CreateTime** | int | 资源创建时间戳 |**Yes**|
| **ExpireTime** | int | 资源过期时间戳 |**Yes**|
| **Expire** | boolean | 是否过期 |**Yes**|
| **BandwidthPackage** | int | globalssh Ultimate带宽包大小 |No|
| **ForwardRegion** | string | InstanceType为Basic版本时，需要展示具体分配的转发机房 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeGlobalSSHInstance
&ProjectId=org-xxxx
&InstanceId=uga-xxxx
```

### 响应示例
    
```json
{
  "Action": "DescribeGlobalSSHInstanceResponse",
  "InstanceSet": [
    {
      "AcceleratedIP": "1.1.2.2",
      "AcceleratingDomain": "1.1.2.2.ipssh.net",
      "ChargeType": "Month",
      "CreationTime": "2018-06-28",
      "ExpirationTime": "2018-06-30",
      "InstanceId": "uga-xxxx",
      "InstanceType": "Basic",
      "Name": "SSH加速",
      "Port": 22,
      "RSPort:": 22
    }
  ],
  "RetCode": 0
}
```





