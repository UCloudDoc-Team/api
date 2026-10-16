# 获取ServerModel列表。 - DescribeUPhoneServerModel

## 简介

获取ServerModel列表。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneServerModel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ServerModelNames.N** | string | 【数组】要获得信息的 ServerModel 名称。调用方式举例：ServerModelNames.0=希望获取信息的 ServerModel1，ServerModelNames.1=ServerModel2。 如果不传入，则返回当前 城市 所有符合条件的 ServerModel。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | ServerModelInstance总数 |**Yes**|
| **Stock** | array[[*StockInfo*](#StockInfo)] | 服务器model的库存 |No|
| **ServerModels** | array[[*ServerModelInstance*](#ServerModelInstance)] | ServerModel实例列表，每项参数可见数据模型 ServerModelInstance |No|

#### 数据模型


#### StockInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ModelName** | string | ServerModel名称 |No|
| **StockCount** | int | 资源余量 |No|

#### ServerModelInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ServerModelName** | string | ServerModel名称	 |No|
| **CPU** | int | 虚拟CPU核数。可选参数：1-64（具体机型与CPU的对应关系参照控制台）。 |No|
| **Memory** | int | 内存大小。单位：MB。 |No|
| **DiskSet** | array[[*ServerDiskSet*](#ServerDiskSet)] | 磁盘信息见 UPhoneDiskSet	 |No|
| **GPUType** | string | GPU类型	 |No|
| **GPU** | int | GPU个数	 |No|
| **UPhoneSpecs** | array[[*UPhoneSpec*](#UPhoneSpec)] | 【数组】手机说明，包含该服务器规格所能创建的手机规格名及对应手机开数。每项参数可见数据模型 [UPhoneSpec](#UPhoneSpec)	 |No|
| **ServerModelState** | string | 表示该机型是否上线，用于前端判断是否开放给用户。枚举值：<br />>AVAILABLE，开放<br />>UNAVAILABLE, 不开放 |No|

#### ServerDiskSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DiskType** | string | 磁盘类型。请参考磁盘类型。 |**Yes**|
| **IsBoot** | boolean | 是否是系统盘。枚举值：<br /><br />> True，是系统盘<br /><br />> False，是数据盘（默认）。Disks数组中有且只能有一块盘是系统盘。 |**Yes**|
| **Size** | int | 磁盘大小，单位: GB |**Yes**|

#### UPhoneSpec

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UPhoneModelName** | string | 手机规格名 |No|
| **UPhoneCount** | int | 手机开数，即该服务器规格能生成对应手机规格的云手机个数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneServerModel
&ProjectId=krGboskq
&CityId=HmUnOIgF
&ServerModelNames.N=UXMldLEe
&Offset=4
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneServerModelResponse",
  "Message": "ssQIxMlq",
  "RetCode": 0,
  "ServerModels": [
    {
      "CPU": 7,
      "DiskSet": [
        {
          "DiskType": "cJLszXWG",
          "IsBoot": true,
          "Size": 5
        }
      ],
      "GPU": 2,
      "GPUType": "OkEaQKtJ",
      "Memory": 6,
      "ServerModelName": "vKFljdot",
      "ServerModelState": "qYJfcaJW",
      "UPhoneSpecs": [
        {
          "UPhoneCount": 2,
          "UPhoneModelName": "yxKzoPlr"
        }
      ]
    }
  ],
  "Stock": "XaUtljEV",
  "TotalCount": 7
}
```





