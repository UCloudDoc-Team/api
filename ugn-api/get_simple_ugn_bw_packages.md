# 获取云联网内的简洁版带宽包 - GetSimpleUGNBwPackages

## 简介

获取指定云联网内的带宽包






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSimpleUGNBwPackages)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSimpleUGNBwPackages`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string | UGN ID |**Yes**|
| **Offset** | int | 偏移量，默认0 |No|
| **Limit** | int | 	<br />分页大小，默认20 |No|
| **PackageIds.N** | string | 带宽包ID列表，不填查询UGN下全部带宽包 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BwPackages** | array[[*SimpleBwPackage*](#SimpleBwPackage)] | 带宽包列表 |**Yes**|
| **TotalCount** | int | 带宽包数量 |**Yes**|
| **Offset** | int | 偏移量 |**Yes**|
| **Limit** | int | 分页大小 |**Yes**|

#### 数据模型


#### SimpleBwPackage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PackageID** | string | 带宽包 ID |**Yes**|
| **UGNID** | string | UGN ID |**Yes**|
| **PayMode** | string | 计费模式 FixedBw:固定带宽｜Peak95:经典95｜Max5:第五峰值｜Traffic:流量计费 |**Yes**|
| **RegionA** | string | 地域A名称 |**Yes**|
| **RegionB** | string | 地域B名称 |**Yes**|
| **BandWidth** | float | 带宽值 |**Yes**|
| **Qos** | string | 服务质量<br />Diamond:钻石｜Platinum:铂金｜Gold:黄金 |**Yes**|
| **Path** | string | 智能路径<br />Delay:最低时延｜IGP:普通线路｜TCO:最低成本 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Name** | string | 带宽包名称 |No|
| **Remark** | string | 备注 |No|
| **ExpireTime** | int | 过期时间 |No|
| **ChangeStatus** | int | 带宽包切换状态 |No|
| **ChangeTime** | int | 带宽包切换时间 |No|
| **ChangePayMode** | string | 带宽包切换计费类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSimpleUGNBwPackages
&ProjectId=org-1jzytw
&UGNID=ugn-1nnk7s9fw238
&Offset=1
&Limit=20
&PackageIds.n=bw-1rr07fd1f2bl
```

### 响应示例
    
```json
{
  "Action": "GetSimpleUGNBwPackagesResponse",
  "BwPackages": [
    {
      "BandWidth": 5,
      "CreateTime": 1781691740,
      "ExpireTime": 1782835200,
      "Name": "test",
      "PackageID": "bw-1rr07fd1f2bl",
      "Path": "IGP",
      "PayMode": "FixedBw",
      "Qos": "Platinum",
      "RegionA": "cn-bj2",
      "RegionB": "cn-sh2",
      "UGNID": "ugn-1nnk7s9fw238"
    }
  ],
  "Limit": 20,
  "Message": "ok",
  "Offset": 0,
  "RetCode": 0,
  "TotalCount": 1
}
```





