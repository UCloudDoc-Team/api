# 获取Bucket信息 - DescribeBucket

## 简介

获取Bucket的描述信息

?> 注意：如果提供了参数BucketName，则参数Offset和Limit失效。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBucket)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBucket`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 如果提供此参数，则获取相应地域下所有空间的空间名称(只返回空间名称信息) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BucketName** | string | 待获取Bucket的名称，若不提供，则获取所有Bucket |No|
| **Offset** | int | 获取所有Bucket列表的偏移数目，默认为0 |No|
| **Limit** | int | 获取所有Bucket列表的限制数目，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileBucketSet*](#UFileBucketSet)] | Bucket的描述信息 参数见 UFileBucketSet |No|

#### 数据模型


#### UFileBucketSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | Bucket所属地域 |No|
| **BucketName** | string | Bucket名称 |No|
| **BucketId** | string | Bucket的ID |No|
| **Domain** | [*UFileDomainSet*](#UFileDomainSet) | Bucket的域名集合 参数见 UFileDomainSet |No|
| **CdnDomainId** | array[string] | 与Bucket关联的CND加速域名的ID列表 |No|
| **Type** | string | Bucket访问类型 |No|
| **CreateTime** | int | Bucket的创建时间 |No|
| **ModifyTime** | int | Bucket的修改时间 |No|
| **Biz** | string | Bucket所属业务, general或vod或udb general: 普通业务； vod: 视频云业务; udb: 云数据库业务 |No|
| **Tag** | string | 所属业务组 |No|
| **HasUserDomain** | int | 是否存在自定义域名。0不存在，1存在，2错误 |No|

#### UFileDomainSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Src** | array[string] | 源站域名 |No|
| **Cdn** | array[string] | UCDN加速域名 |No|
| **CustomSrc** | array[string] | 用户自定义源站域名 |No|
| **CustomCdn** | array[string] | 用户自定义CDN加速域名 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeBucket
&BucketName=blue
&Region=cxqbTMaU
```

### 响应示例
    
```json
{
  "Aciton": "DescribeBucketResponse",
  "DataSet": [
    {
      "Biz": "general",
      "BucketId": "ufile-xxx",
      "BucketName": "blue",
      "CdnDomainId": [
        "ucdn-xxx"
      ],
      "CreateTime": 1409736300,
      "Domain": {
        "Cdn": [
          "blue.ufile.ucloud.com.cn"
        ],
        "CustomCdn": [],
        "CustomSrc": [],
        "Src": [
          "blue.ufile.ucloud.cn"
        ]
      },
      "HasUserDomain": 1,
      "ModifyTime": 1409736300,
      "Region": "cn-bj2",
      "Tag": "dddd",
      "Type": "public"
    }
  ],
  "Retcode": 0
}
```





