# 查询已购买的资源包列表 - DescribeUFilePkg

## 简介

查询已购买的资源包列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFilePkg)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFilePkg`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | 查询指定的资源包，当指定ResourceId查询时，Region是必填的 |No|
| **Expired** | int | 默认0表示查询全部已购买的资源包，1表示查询过期的，-1表示查询非过期的 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Pkgs** | array[[*UFilePkg*](#UFilePkg)] | 已购买的资源包 |**Yes**|

#### 数据模型


#### UFilePkg

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 资源包地域 |**Yes**|
| **ResourceId** | string | 资源包ID |No|
| **PkgName** | string | 资源包名称 |No|
| **PkgType** | int | 资源包类型ID |No|
| **Amount** | int | 资源包容量 |No|
| **RemainAmount** | string | 资源包剩余容量（仅支持流量包） |No|
| **CreateTime** | int | 资源包创建时间 |No|
| **ExpiredTime** | int | 资源包失效时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFilePkg
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=xhsJdhxW
&ResourceId=qcurMiDR
&Exprired=0
&Expired=0
```

### 响应示例
    
```json
{
  "Action": "DescribeUFilePkgResponse",
  "Pkgs": [
    {
      "Amount": 4,
      "CreateTime": 9,
      "ExpiredTime": 9,
      "PkgType": 8,
      "RemainAmount": "tBdjYLgy",
      "ResourceId": "TNMDmPhR"
    }
  ],
  "RetCode": 0
}
```





