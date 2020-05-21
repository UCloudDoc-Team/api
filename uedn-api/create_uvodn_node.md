# 创建节点 - CreateUvodnNode

## 简介

创建节点v2.0








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUvodnNode`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **IdcId** | string | 机房id |**Yes**|
| **CpuCore** | int | cpu核心数 |**Yes**|
| **MemSize** | int | 内存大小，单位GB |**Yes**|
| **DiskSize** | int | 数据盘大小，单位GB |**Yes**|
| **ImageId** | string | 镜像ID |**Yes**|
| **NetLimit** | int | 节点带宽限制，单位Mbs |**Yes**|
| **NodeName** | string | 节点名称 |No|
| **SysDiskSize** | int | 系统盘大小，单位GB， 默认20GB |No|
| **AccountName** | string | 账户名，默认root |No|
| **PassWord** | string | 密码 |No|
| **NodeCount** | int | 创建节点数量，默认1 |No|
| **ChargeType** | int | 付费方式，1按时，2按月，3按年，默认2 |No|
| **ChargeQuantity** | int | 月数或者年数，0计费到月底， 默认0 |No|
| **SubnetId** | string | 子网ID |No|
| **ProductType** | string | 产品类型：normal（标准型），hf（高频型） |No|
| **FirewallId** | string | 外网防护墙规则租，默认 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeList** | array[string] | 节点id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUvodnNode
&ProjectId=org-xxx
&IdcId=uedn-idc-xxx
&CpuCore=1
&MemSize=2
&ImageId=uedn-image-xxx
&NetLimit=2
&NodeName=test
&SysDiskSize=20
&AccountName=root
&PassWord=xxx
&NodeCount=1
&ChargeType=2
&ChargeQuantity=1
&ProductType=TUYiObQi
&FirewallId=YavTnexR
```

### 响应示例
    
```json
{
  "Action": "CreateUvodnNodeResponse",
  "NodeList": [
    {
      "NodeId": "uedn-node-xxx"
    }
  ],
  "RetCode": 0
}
```





