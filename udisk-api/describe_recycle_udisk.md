# 拉取回收站中云硬盘列表 - DescribeRecycleUDisk

## 简介

拉取回收站中云硬盘列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeRecycleUDisk)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeRecycleUDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Limit** | int | 返回数据长度, 默认为20 |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 磁盘数量 |**Yes**|
| **DataSet** | array[[*RecycleUDiskSet*](#RecycleUDiskSet)] | 回收站磁盘列表 |No|

#### 数据模型


#### RecycleUDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UDiskId** | string | 磁盘id |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ExpiredTime** | int | 过期时间 |**Yes**|
| **CountdownTime** | int | 销毁倒计时 |**Yes**|
| **Name** | string | 磁盘名称 |**Yes**|
| **Size** | int | 磁盘容量 |**Yes**|
| **Tag** | string | 业务组 |No|
| **Zone** | string | 可用区 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeRecycleUDisk
&Region=cn-bj2
&Zone=cn-bj2-02
&Project=org-xxx
&Limit=20
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "DescribeRecycleUDiskResponse",
  "DataSet": [
    {
      "CountdownTime": 602781,
      "CreateTime": 1508469548,
      "ExpiredTime": 1510309558,
      "Name": "sniper",
      "Size": 20,
      "Tag": "Default",
      "UDiskId": "bs-xxx",
      "Zone": "cn-bj2-02"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





