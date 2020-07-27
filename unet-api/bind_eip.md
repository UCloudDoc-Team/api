# 绑定弹性IP - BindEIP

## 简介

将尚未使用的弹性IP绑定到指定的资源






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BindEIP)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BindEIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写 |No|
| **EIPId** | string | 弹性IP的资源Id |**Yes**|
| **ResourceType** | string | 弹性IP请求绑定的资源类型, 枚举值为: uhost: 云主机; ulb, 负载均衡器 upm: 物理机; hadoophost: 大数据集群;fortresshost：堡垒机；udockhost：容器；udhost：私有专区主机；natgw：natgw；udb：udb；vpngw：ipsec vpn；ucdr：云灾备；dbaudit：数据库审计；uni：虚拟网卡。如果EIP为普通带宽计费，且带宽值高于2G，则只允许绑定在快杰型云主机和ULB |**Yes**|
| **ResourceId** | string | 弹性IP请求绑定的资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BindEIP
&Region=cn-bj2
&EIPId=eip-XXXX
&ResourceType=uhost
&ResourceId=uhost-XXXXX
```

### 响应示例
    
```json
{
  "Action": "BindEIPResponse",
  "Request_uuid": "1b52baa6-01ea-4cba-a6f9-XXXXXXXX",
  "RetCode": 0
}
```





