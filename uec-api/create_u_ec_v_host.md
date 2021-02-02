# 创建虚拟机 - CreateUEcVHost

## 简介

创建虚拟机v2.0









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUEcVHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
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
| **FirewallId** | string | 外网防护墙规则组，默认 |No|
| **IsNeedOuterIp** | string | 是否关联外网IP，（yes-是，no-否，默认yes） |No|
| **Isp.N** | int | 运营商（1-电信，2-联通，4移动） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NodeList** | array[[*NodeList*](#NodeList)] | 节点id（详情参考NodeList） |**Yes**|

#### 数据模型


#### NodeList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NodeId** | string | 虚拟机资源id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUEcVHost
&ProjectId=YxGkkTQL
&IdcId=jIDjwIdN
&CpuCore=9
&MemSize=6
&DiskSize=1
&ImageId=wPqVbfPI
&NetLimit=9
&NodeName=RjAajccJ
&SysDiskSize=8
&AccountName=YHfiLzcA
&PassWord=mosikhrs
&NodeCount=2
&ChargeType=4
&ChargeQuantity=4
&SubnetId=iYsMFYAL
&ProductType=VbeHyCVn
&FirewallId=UUvBPRWu
&IsNeedOuterIp=QCwrnAIL
&Isp.n=3
```

### 响应示例
    
```json
{
  "Action": "CreateUEcVHostResponse",
  "NodeList": [
    {
      "NodeId": "dgMyDmAG"
    }
  ],
  "RetCode": 0
}
```





