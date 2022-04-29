# 获取云手机规格列表 - DescribeUPhoneModel

## 简介











## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneModel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UPhoneModelNames.N** | string | 【数组】要获得信息的 UPhoneModel 名称。调用方式举例：UPhoneModelNames.0=希望获取信息的 UPhoneModel1，UPhoneModelNames.1=UPhoneModel2。 如果不传入，则返回当前 城市 所有符合条件的 UPhoneModel。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | UPhoneModelInstance总数 |**Yes**|
| **UPhoneModels** | array[[*UPhoneModelInstance*](#UPhoneModelInstance)] | UPhoneModel实例列表，具体参数可见 UPhoneModelInstance |**Yes**|

#### 数据模型


#### UPhoneModelInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPhoneModelName** | string | UPhoneModel名称 |**Yes**|
| **CPU** | int | 虚拟CPU核数。 |**Yes**|
| **Memory** | int | 内存大小。单位MB |**Yes**|
| **DiskSize** | int | 磁盘大小，单位: GB |**Yes**|
| **Resolution** | string | 分辨率 |**Yes**|
| **Refresh** | int | 刷新率 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneModel
&Region=cn-zj
&ProjectId=boBtideL
&UPhoneModelNames.N=BPlanZIw
&Offset=8
&Limit=7
&CityId=pKekkCXR
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneModelResponse",
  "Message": "WcgStfDK",
  "RetCode": 0,
  "TotalCount": 3,
  "UPhoneModels": [
    "XeMATaVc"
  ]
}
```





