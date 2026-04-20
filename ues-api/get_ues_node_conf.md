# 获取节点配置列表 - GetUESNodeConf

## 简介

获取节点配置列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUESNodeConf)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUESNodeConf`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 所有节点配置信息的个数 |**Yes**|
| **NodeConfList** | array[[*NodeConf*](#NodeConf)] | 服务节点配置信息列表 |**Yes**|

#### 数据模型


#### NodeConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Memory** | int | 内存，单位为GB |**Yes**|
| **CPU** | int | CPU数量 |**Yes**|
| **NodeConf** | string | 节点配置标识 |**Yes**|
| **DiskType** | string | 磁盘类型[RSSD\|SSD] |**Yes**|
| **DiskSize** | int | 磁盘大小，单位为GB |**Yes**|
| **IsSecGroup** | boolean | 是否支持安全组[true\|false] |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUESNodeConf
&Region=cn-zj
&Zone=cn-zj-01
&InUsed=0
```

### 响应示例
    
```json
{
  "Action": "GetUESNodeConfResponse",
  "Message": "iKHTcoAa",
  "RetCode": 0,
  "TotalCount": 12,
  "UESNodeConfList": [
    {
      "CPU": 2,
      "DiskSize": 200,
      "DiskType": "SATA",
      "InUsed": 1,
      "Memory": 6,
      "NodeConf": "ds1.large",
      "NodeType": "compute"
    },
    {
      "CPU": 1,
      "DiskSize": 100,
      "DiskType": "SATA",
      "InUsed": 1,
      "Memory": 4,
      "NodeConf": "ms1.large",
      "NodeType": "master"
    },
    {
      "CPU": 2,
      "DiskSize": 100,
      "DiskType": "SATA",
      "InUsed": 1,
      "Memory": 8,
      "NodeConf": "ms1.xlarge",
      "NodeType": "master"
    }
  ]
}
```





