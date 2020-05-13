# 获取镜像仓库下的镜像 - GetRepoImage

## 简介

获取镜像仓库下的镜像





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetRepoImage)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetRepoImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **RepoName** | string | 镜像仓库名称 |**Yes**|
| **Offset** | int | 偏移量，默认0 |No|
| **Limit** | int | 显示数量，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int |  |**Yes**|
| **ImageSet** | array[[*ImageSet*](#ImageSet)] | 镜像列表 |**Yes**|

#### 数据模型


#### ImageSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ImageName** | string | 镜像名称 |**Yes**|
| **PullCount** | int | 镜像被下载次数 |**Yes**|
| **CreateTime** | string | 创建时间 |**Yes**|
| **UpdateTime** | string | 修改时间 |**Yes**|
| **LatestTag** | string | 最新push的Tag |**Yes**|
| **RepoName** | string | 镜像仓库名称 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetRepoImage
&ProjectId=bbrEuvfC
&RepoName=idkTdEFo
&Offset=6
&Limit=6
&ProjectId=WsHgZAjU
```

### 响应示例
    
```json
{
  "Action": "GetRepoImageResponse",
  "ImageSet": [
    {
      "CreateTime": 5,
      "ImageName": "dCVBnkxg",
      "LatestTag": "iBvvYGkW",
      "PullCount": 4,
      "UpdateTime": 7
    },
    {
      "CreateTime": 2,
      "ImageName": "HxZkUXvp",
      "LatestTag": "KNyBVrNA",
      "PullCount": 2,
      "UpdateTime": 2
    },
    {
      "CreateTime": 2,
      "ImageName": "qCHiVQXX",
      "LatestTag": "dnvIjkJY",
      "PullCount": 6,
      "UpdateTime": 6
    },
    {
      "CreateTime": 9,
      "ImageName": "lJszSnED",
      "LatestTag": "wGBJBifW",
      "PullCount": 1,
      "UpdateTime": 8
    },
    {
      "CreateTime": 7,
      "ImageName": "BfChDnxj",
      "LatestTag": "CdySnxrY",
      "PullCount": 9,
      "UpdateTime": 1
    },
    {
      "CreateTime": 9,
      "ImageName": "HUTQywVu",
      "LatestTag": "zqXMWiRd",
      "PullCount": 1,
      "UpdateTime": 9
    },
    {
      "CreateTime": 8,
      "ImageName": "QfwwaABh",
      "LatestTag": "EymhuHfx",
      "PullCount": 7,
      "UpdateTime": 9
    },
    {
      "CreateTime": 5,
      "ImageName": "ThYJXrVc",
      "LatestTag": "dnXrJOti",
      "PullCount": 4,
      "UpdateTime": 2
    },
    {
      "CreateTime": 2,
      "ImageName": "qzCGPhQD",
      "LatestTag": "MCnyUuwU",
      "PullCount": 6,
      "UpdateTime": 3
    }
  ],
  "RetCode": 0,
  "TotalCount": 5
}
```





