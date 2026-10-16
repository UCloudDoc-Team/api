# 获取虚拟机调整差价 - GetUEcUpgradePrice

## 简介

获取虚拟机调整差价









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEcUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeId** | string | 虚拟机资源ID |**Yes**|
| **CpuCore** | int | cpu核心数 |No|
| **MemSize** | int | 内存大小，单位GB |No|
| **SysDiskSize** | int | 系统盘大小，单位GB |No|
| **DiskSize** | int | 数据盘大小，单位GB |No|
| **NetLimit** | int | 节点带宽限制，单位Mbs |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 规格调整差价 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEcUpgradePrice
&ProjectId=gzaeLuxk
&NodeId=AwRowCGB
&CpuCore=4
&MemSize=3
&SysDiskSize=2
&DiskSize=6
&NetLimit=1
```

### 响应示例
    
```json
{
  "Action": "GetUEcUpgradePriceResponse",
  "Price": 6,
  "RetCode": 0
}
```





