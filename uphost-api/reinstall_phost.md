# 重装物理机 - ReinstallPHost

## 简介

重装物理机操作系统

?> 密码需要通过base64进行编码<br /><br /># echo password1 \| base<br />ugfzc3dvcmqxcg==




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ReinstallPHost)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ReinstallPHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PHostId** | string | PHost资源ID |**Yes**|
| **Password** | string | 密码 |**Yes**|
| **ImageId** | string | 镜像Id，参考镜像列表，默认使用原镜像 |No|
| **Name** | string | 物理机名称，默认不更改 |No|
| **Remark** | string | 物理机备注，默认为不更改。 |No|
| **Tag** | string | 业务组，默认不更改。 |No|
| **ReserveDisk** | string | 是否保留数据盘，保留：Yes，不报留：No， 默认：Yes |No|
| **Raid** | string | 不保留数据盘重装，可选Raid |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PHostId** | string | PHost 的资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ReinstallPHost
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&PHostId=upm-xxx
&Password=xxx
&ImageId=pimg-xxx
&Name=123
&ReserveDisk=Yes
```

### 响应示例
    
```json
{
  "Action": "ReinstallPHostResponse",
  "PHostId": "upm-xxx",
  "RetCode": 0
}
```





