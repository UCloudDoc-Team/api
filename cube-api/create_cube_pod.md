# 创建Pod - CreateCubePod

## 简介

创建Pod









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCubePod`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **VPCId** | string | VPCId |**Yes**|
| **SubnetId** | string | 子网Id |**Yes**|
| **Pod** | string | base64编码的Pod的yaml。大小不超过16KB |**Yes**|
| **Group** | string | pod所在组 |No|
| **Name** | string | pod的名字 |No|
| **Tag** | string | 业务组。默认：Default（Default即为未分组） |No|
| **CpuPlatform** | string | Cpu平台（V6：Intel、A2：AMD），默认V6。支持的地域（北京2B、北京2E、上海2A、广东、香港 、东京）目前北京2E仅有A2，其余地域仅有V6 |No|
| **ChargeType** | string | 计费模式。枚举值为： <br /><br /> > Year，按年付费； <br /><br /> > Month，按月付费；<br /><br /> > Postpay， <br /><br /> 后付费；默认为后付费 |No|
| **Quantity** | int | 购买时长。默认:值 1。 月付时，此参数传0，代表购买至月末。 |No|
| **CouponId** | string | 代金券ID。请通过DescribeCoupon接口查询，或登录用户中心查看 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Pod** | string | base64编码的yaml |**Yes**|
| **CubeId** | string | cube的资源Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCubePod
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=pndYiaRN
&VPCId=URTXzGZi
&SubnetId=uXbcciNB
&Pod=siMmEMEZ
&BusinessId=zxQytWtb
&Group=ksLiPLbC
&Name=VzPwOZLL
&CpuPlatform=ToOJZHvR
&CpuPlatform=cDYXouhW
&ChargeType=iZfEqMCC
&ChargeType=thtWusXL
&Quantity=4
&CouponId=TkrdYMXF
```

### 响应示例
    
```json
{
  "Action": "CreateCubePodResponse",
  "CubeId": "VrRtcHeJ",
  "Pod": "QYQSVWuz",
  "RetCode": 0
}
```





