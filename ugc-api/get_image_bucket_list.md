# 获取可用的镜像仓库列表 - GetImageBucketList

## 简介

获取可用的Docker镜像仓库列表，包括公有和私有的。





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetImageBucketList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetImageBucketList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **BucketName** | string | Docker镜像仓库名称，不填返回所有的镜像仓库 |No|
| **BucketType** | string | All：用户所有可见的仓库， User：用户个人创建的仓库 ， Share：第三方公开镜像， 默认值：All |No|
| **OrderBy** | string | Default: 默认排序 |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的镜像总数 |No|
| **ImageSet** | array[[*ImageBucketListSet*](#ImageBucketListSet)] | 镜像列表，详见 ImageBucketListSet |No|

#### 数据模型


#### ImageBucketListSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketName** | string | Docker镜像仓库名称 |No|
| **BucketType** | string | Private：私有，Public：公有 |No|
| **ImageCount** | int | 仓库中含有的镜像个数 |No|
| **CreateTime** | int | 创建时间，格式为Unix时间戳 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetImageBucketList
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "GetImageBucketListResponse",
  "ImageSet": [
    {
      "BucketName": "ucsdr.ucloud.cn:5000/ucs/helloworld:6",
      "BucketType": "Public",
      "CreateTime": 1234567890,
      "ImageCount": 10
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





