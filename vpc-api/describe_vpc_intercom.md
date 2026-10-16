# 获取VPC互通信息 - DescribeVPCIntercom

## 简介

获取VPC互通信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeVPCIntercom)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeVPCIntercom`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 源VPC所在地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 源VPC所在项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPCId** | string | VPC短ID |**Yes**|
| **DstRegion** | string | 目的VPC所在地域，默认为全部地域 |No|
| **DstProjectId** | string | 目的项目ID，默认为全部项目 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*VPCIntercomInfo*](#VPCIntercomInfo)] | 联通VPC信息数组 |No|

#### 数据模型


#### VPCIntercomInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目Id |No|
| **VPCType** | int | vpc类型（1表示托管VPC，0表示公有云VPC） |**Yes**|
| **AccountId** | int | 项目Id（数字） |**Yes**|
| **Network** | array[string] | VPC的地址空间<br /> |No|
| **DstRegion** | string | 所属地域 |No|
| **Name** | string | VPC名字 |No|
| **VPCId** | string | VPCId |No|
| **Tag** | string | 业务组（未分组显示为 Default） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeVPCIntercom
&Region=cn-sh2
&ProjectId=org-XXX
&VPCId=uvnet-XXXX
&HasHybrid=1
&HasHybrid=6
&HasHybrid=7
&HasHybrid=6
```

### 响应示例
    
```json
{
  "Action": "DescribeVPCIntercomResponse",
  "DataSet": [
    {
      "DstRegion": "ge-fra",
      "Name": "DefaultVPC",
      "Network": [
        "10.29.XX.0/16"
      ],
      "ProjectId": "org-XXXXX",
      "Tag": "Default",
      "VPCId": "uvnet-XXXXX"
    },
    {
      "DstRegion": "cn-sh2",
      "Name": "ulb-vpc",
      "Network": [
        "172.16.XX.0/12",
        "10.1.XX.0/16"
      ],
      "ProjectId": "org-XXX",
      "Remark": "",
      "Tag": "Default",
      "VPCId": "uvnet-XXXX"
    }
  ],
  "RetCode": 0
}
```





