# 批量申请虚拟网卡辅助IP - AllocateBatchSecondaryIp

## 简介

批量申请虚拟网卡辅助IP

?> Ip和Count同时仅允许一个有参




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateBatchSecondaryIp)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateBatchSecondaryIp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Mac** | string | 节点mac |**Yes**|
| **ObjectId** | string | 资源Id |**Yes**|
| **SubnetId** | string | 子网Id（若未指定，则根据zone获取默认子网进行创建） |No|
| **VPCId** | string | vpcId |No|
| **Ip.N** | string | 【arry】支持按如下方式申请：①按网段：如192.168.1.32/27，掩码数字最小为27   ②指定IP地址，如192.168.1.3 |No|
| **Count** | int | 申请的内网IP数量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IpsInfo** | array[[*IpsInfo*](#IpsInfo)] | 详见IpsInfo |**Yes**|

#### 数据模型


#### IpsInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string | 内网IP地址 |No|
| **Mask** | string | 掩码 |No|
| **Gateway** | string | 网关 |No|
| **Mac** | string | MAC地址 |No|
| **SubnetId** | string | 子网资源ID |No|
| **VPCId** | string | VPC资源ID |No|
| **Status** | [*StatusInfo*](#StatusInfo) | IP分配结果，详见StatusInfo |No|

#### StatusInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StatusCode** | string | 枚举值：Succeeded，Failed |No|
| **Message** | string | IP分配失败原因 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateBatchSecondaryIp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XgPNpstA
&Mac=HHbZOKcj
&ObjectId=OidCZWsV
&SubnetId=XFAATutN
&VPCId=ZlXtGxKD
&Ip.N=ZhaZYRqX
&Count=7
```

### 响应示例
    
```json
{
  "Action": "AllocateBatchSecondaryIpResponse",
  "IpInfo": [
    {
      "Gateway": "pSmgKDHW",
      "Ip": "kfVBsTcw",
      "Mac": "MPJCarZQ",
      "Mask": "HbZJCMWG",
      "Status": [
        {
          "Message": "CIEfBloY",
          "StatusCode": "vvInRaak"
        }
      ],
      "SubnetId": "dnSKxsEH",
      "VPCId": "jfctXBmr"
    }
  ],
  "RetCode": 0
}
```





