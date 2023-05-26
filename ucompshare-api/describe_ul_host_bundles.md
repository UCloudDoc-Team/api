# 获取轻量应用云主机套餐列表 - DescribeULHostBundles

## 简介

获取轻量应用云主机套餐列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeULHostBundles`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Bundles** | array[[*Bundle*](#Bundle)] | 套餐列表 |**Yes**|

#### 数据模型


#### Bundle

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BundleId** | string | 套餐ID。 |No|
| **CPU** | int | CPU核数。 |No|
| **Memory** | int | 内存大小。单位：MB。 |No|
| **SysDiskSpace** | int | 系统盘大小。单位：GB。 |No|
| **Bandwidth** | int | 外网带宽。单位：Mbps。 |No|
| **TrafficPacket** | int | 流量包大小。单位：GB。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeULHostBundles
&Region=cn-zj
&ProjectId=TllZIUhl
```

### 响应示例
    
```json
{
  "Action": "DescribeULHostBundlesResponse",
  "Bundles": [
    {
      "Bandwidth": 6,
      "BundleId": "SqTRbDJZ",
      "CPU": 1,
      "Memory": 8,
      "SysDiskSpace": 5,
      "TrafficPacket": 8
    }
  ],
  "Message": "RHvGhTzX",
  "RetCode": 0
}
```





