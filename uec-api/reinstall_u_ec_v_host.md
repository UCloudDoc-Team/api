# 虚拟机重装系统 - ReinstallUEcVHost

## 简介

虚拟机重装系统









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ReinstallUEcVHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NodeId** | string | 虚拟机资源ID |**Yes**|
| **ImageId** | string | 镜像ID |**Yes**|
| **KeepData** | int | 是否保留数据盘数据， 0-不保留，1-保留，默认为1 |No|
| **Password** | string | 节点密码 |No|
| **SysDiskSize** | int | 系统盘大小，单位GB |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ReinstallUEcVHost
&ProjectId=jRooBFoF
&NodeId=LQqqwWZR
&ImageId=PXFPLzFR
&KeepData=6
&Password=lDnEdOtx
&SysDiskSize=5
```

### 响应示例
    
```json
{
  "Action": "ReinstallUEcVHostResponse",
  "RetCode": 0
}
```





