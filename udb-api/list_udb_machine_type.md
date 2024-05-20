# 获取UDB云数据库计算规格列表 - ListUDBMachineType

## 简介

获取UDB云数据库支持的计算规格列表，暂不支持获取跨可用区实例的计算规格，目前支持的数据库品类包括：NVMe版和SSD云盘版MySQL






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUDBMachineType)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUDBMachineType`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 默认是"Normal" |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*MachineType*](#MachineType)] | 计算规格列表 |**Yes**|
| **DefaultMachineType** | [*MachineType*](#MachineType) | 默认计算规格 |**Yes**|

#### 数据模型


#### MachineType

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 计算规格id, 目前支持CPU和内存比1:2、1:4、1:8三类配比规格;<br /><br />规格的格式为："机型.配比.CPU核数规格"；<br /><br />机型支持o和n两种机型，分别代表快杰NVMe和SSD云盘机型；<br /><br />配比映射关系如下:<br />2m代表CPU内存配比1比2，<br />4m代表CPU内存配比1比4，<br />8m代表CPU内存配比1比8，<br /><br />CPU核数规格射关系如下：<br />small代表1C，<br />medium代表2C，<br />xlarge代表4C，<br />2xlarge代表8C，<br />4xlarge代表16C，<br />8xlarge代表32C，<br />16xlarge代表64C，<br /><br />例如 "o.mysql4m.medium"表示<br />创建快杰NVMe机型2C8G的实例，<br />"o.mysql8m.4xlarge"表示创建快杰NVMe机型16C128G的实例<br /> |No|
| **Description** | string | 计算规格描述，格式为"nCmG"，表示n核mG内存实例 |No|
| **Cpu** | int | 规格cpu核数 |No|
| **Memory** | int | 规格内存大小，单位（GB） |No|
| **Os** | string | 内部云主机机型，可选"o/n" |No|
| **Group** | string | 内存/cpu配比 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUDBMachineType
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=JmoFMucA
&InstanceMode=xepGsMAp
&RegionFlag=HbtnSAmN
```

### 响应示例
    
```json
{
  "Action": "ListUDBMachineTypeResponse",
  "DataSet": [
    {
      "Cpu": 9,
      "Description": "phSdctBk",
      "Group": "NMGNcZoB",
      "ID": "jlzxzRpr",
      "Memory": 8,
      "Os": "mXvRGwSp"
    }
  ],
  "DefaultMachineType": {},
  "Message": "gpbNNqbc",
  "RetCode": 0
}
```





