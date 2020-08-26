# 更改资源池配置 - ResizeUDSet

## 简介

更改资源池配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ResizeUDSet)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResizeUDSet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | int | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **HostId** | string | 资源池的短ID |**Yes**|
| **Memory** | int | 内存大小, 单位: MB, 范围[65536，163840], 步长: 32768, 默认值: 131072 |No|
| **DiskSpace** | int | 数据盘大小, 单位: GB, 范围[4096,6144], 步长: 2048, 默认值: 6144 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **HostId** | string | 资源池的短ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn?Action=ResizeUDSet
&Region=CXSrTxMm
&HostId=XtUxjABx
&Memory=114688
&DiskSpace=5120
```

### 响应示例
    
```json
{
  "Action": "ResizeUDSetResponse",
  "HostId": "YuXijDPw",
  "RetCode": 0
}
```





