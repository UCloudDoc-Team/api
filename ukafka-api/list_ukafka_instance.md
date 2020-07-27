# 列举集群信息 - ListUKafkaInstance

## 简介

列举集群信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUKafkaInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUKafkaInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Limit** | string | 默认为60 |No|
| **Offset** | string | 默认为0 |No|
| **Filter** | string | 是否过滤删除了的节点，默认为‘true’ |No|
| **VPCId** | string | VPCId |No|
| **SubnetId** | string | SubnetId |No|
| **BusinessId** | string | BusinessId |No|
| **ClusterInstanceId** | string | 集群ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ClusterSet** | string | 信息 |**Yes**|
| **TotalCount** | string | 总数 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUKafkaInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=psLewFbM
&Limit=LidCsVTz
&Offset=Rtvvkzbo
&Filter=xaSWuIxd
&VPCId=JiyiuaGj
&SubnetId=lpUAUCTy
&BusinessId=HttFFiEn
&ClusterInstanceId=bfibtMTE
```

### 响应示例
    
```json
{
  "Action": "ListUKafkaInstanceResponse",
  "ClusterSet": [
    {
      "AutoRenew": "Yes",
      "BusinessId": "",
      "ChargeType": "Month",
      "ClusterInstanceId": "ukafka-5xagjz",
      "ClusterInstanceName": "test",
      "CreateTime": 1550476133,
      "ExpireTime": 1551369600,
      "Framework": "Kafka",
      "FrameworkVersion": "1.1.1",
      "NewMessage": "Yes",
      "RedundantCount": 0,
      "Remark": "",
      "RunningTime": 5623,
      "State": "Running",
      "SubnetId": "subnet-ah4q5l",
      "Tag": "Default",
      "UHostCount": 3,
      "VPCId": "uvnet-rgi3ym",
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





