# 获取预取任务状态 - DescribeNewUcdnPrefetchCacheTask

## 简介

获取预取任务状态





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNewUcdnPrefetchCacheTask)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNewUcdnPrefetchCacheTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TaskId.N** | string | 提交任务时返回的任务ID |No|
| **BeginTime** | int | 查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值 |No|
| **EndTime** | int | 查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。 |No|
| **Status** | string | 需要获取的内容预热的状态，枚举值：success：成功；wait：等待处理；process：正在处理；failure：失败； unknow：未知，默认选择所有状态 |No|
| **Offset** | int | 数据偏移量，默认为0，自然数 |No|
| **Limit** | int | 返回数据长度,默认全部，自然数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 预热任务的总数 |No|
| **TaskList** | array[[*TaskInfo*](#TaskInfo)] | 预热任务信息，参考TaskInfo |No|

#### 数据模型


#### TaskInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | 提交任务时返回的任务ID |No|
| **UrlLists** | array[[*UrlProgressInfo*](#UrlProgressInfo)] | 任务url的信息列表，参考UrlProgressInfo |No|
| **Type** | string | file/dir  刷新任务会返回Type，预取任务没有 |No|
| **CreateTime** | int | 刷新任务创建的时间。格式为Unix Timestamp |No|
| **Status** | string | 刷新任务的当前状态，枚举值：success：成功；wait：排队中；process：处理中；failure：失败； unknow：未知 |No|

#### UrlProgressInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Url** | string | 刷新的单条url |No|
| **CreateTime** | int | 刷新任务创建的时间。格式为Unix Timestamp |No|
| **FinishTime** | int | 任务完成时间。格式为Unix Timestamp |No|
| **Status** | string | 刷新任务的当前状态，枚举值：success：成功；wait：排队中；process：处理中；failure：失败； unknow：未知 |No|
| **Progress** | int | 刷新进度，单位% |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNewUcdnPrefetchCacheTask
&ProjectId=xxxxx
&TaskId.0=feTvWytY
&BeginTime=2
&EndTime=3
&Status=uwNWouHX
&Offset=1
&Limit=1
```

### 响应示例
    
```json
{
  "Action": "DescribeNewUcdnPrefetchCacheTaskResponse",
  "RetCode": 0,
  "TaskList": [
    {
      "CreateTime": 4,
      "Status": "ySoPLGgE",
      "TaskId": "mEuMcQSL",
      "UrlLists": [
        {
          "CreateTime": 6,
          "FinishTime": 1,
          "Progress": 3,
          "Status": "pmUWBVxw",
          "Url": "xChNHhYo"
        },
        {
          "CreateTime": 3,
          "FinishTime": 7,
          "Progress": 7,
          "Status": "xCZMvZWZ",
          "Url": "lKGDMDQq"
        },
        {
          "CreateTime": 6,
          "FinishTime": 9,
          "Progress": 9,
          "Status": "zMxmxYcf",
          "Url": "ptLqMQuh"
        },
        {
          "CreateTime": 4,
          "FinishTime": 1,
          "Progress": 4,
          "Status": "OaxNseKe",
          "Url": "YhpEnOmI"
        },
        {
          "CreateTime": 4,
          "FinishTime": 5,
          "Progress": 4,
          "Status": "etAmHzPP",
          "Url": "PEBgMeNh"
        }
      ]
    },
    {
      "CreateTime": 1,
      "Status": "JKrNCisb",
      "TaskId": "mYtrUNKc",
      "UrlLists": [
        {
          "CreateTime": 3,
          "FinishTime": 2,
          "Progress": 6,
          "Status": "XynKYAiJ",
          "Url": "XqHsIOtd"
        },
        {
          "CreateTime": 1,
          "FinishTime": 6,
          "Progress": 3,
          "Status": "rCoGJtmC",
          "Url": "EYRxaYAM"
        },
        {
          "CreateTime": 5,
          "FinishTime": 6,
          "Progress": 2,
          "Status": "sFsEYOgd",
          "Url": "ehwfbnDN"
        },
        {
          "CreateTime": 8,
          "FinishTime": 5,
          "Progress": 3,
          "Status": "EwSSKJad",
          "Url": "FxacwAet"
        },
        {
          "CreateTime": 8,
          "FinishTime": 5,
          "Progress": 7,
          "Status": "SkdViYPP",
          "Url": "VRJFzzlH"
        },
        {
          "CreateTime": 5,
          "FinishTime": 3,
          "Progress": 5,
          "Status": "hcAQXhoN",
          "Url": "LwAewYSo"
        },
        {
          "CreateTime": 7,
          "FinishTime": 3,
          "Progress": 2,
          "Status": "AiVaeqAx",
          "Url": "eJpkSqiP"
        }
      ]
    },
    {
      "CreateTime": 7,
      "Status": "dDQVOfuA",
      "TaskId": "ZJazzIIh",
      "UrlLists": [
        {
          "CreateTime": 8,
          "FinishTime": 5,
          "Progress": 2,
          "Status": "okiJCQZU",
          "Url": "qKIoMLtR"
        },
        {
          "CreateTime": 1,
          "FinishTime": 9,
          "Progress": 6,
          "Status": "SXVfOLXG",
          "Url": "fVxMWSUL"
        },
        {
          "CreateTime": 2,
          "FinishTime": 4,
          "Progress": 9,
          "Status": "wOXhjduh",
          "Url": "UtBAuUmZ"
        }
      ]
    },
    {
      "CreateTime": 3,
      "Status": "LeqJkycM",
      "TaskId": "sEiKGYYr",
      "UrlLists": [
        {
          "CreateTime": 6,
          "FinishTime": 8,
          "Progress": 5,
          "Status": "YYcZbXWw",
          "Url": "oEqzcgMA"
        },
        {
          "CreateTime": 1,
          "FinishTime": 6,
          "Progress": 6,
          "Status": "HYZmwEUR",
          "Url": "UKXkiPDK"
        },
        {
          "CreateTime": 2,
          "FinishTime": 2,
          "Progress": 3,
          "Status": "FBCAWBMW",
          "Url": "aGCnxHXv"
        }
      ]
    },
    {
      "CreateTime": 1,
      "Status": "GVWVbBkR",
      "TaskId": "ByScqGMr",
      "UrlLists": [
        {
          "CreateTime": 9,
          "FinishTime": 2,
          "Progress": 4,
          "Status": "iQguQPft",
          "Url": "MmoeVMJQ"
        },
        {
          "CreateTime": 3,
          "FinishTime": 9,
          "Progress": 3,
          "Status": "CPqqNmqO",
          "Url": "YtzBfJQF"
        }
      ]
    },
    {
      "CreateTime": 5,
      "Status": "RPkHZOFJ",
      "TaskId": "sklDNgoJ",
      "UrlLists": [
        {
          "CreateTime": 5,
          "FinishTime": 2,
          "Progress": 8,
          "Status": "hfRtxJYA",
          "Url": "MPKzOnkG"
        },
        {
          "CreateTime": 3,
          "FinishTime": 2,
          "Progress": 8,
          "Status": "NOgImUxr",
          "Url": "NqeqhcDn"
        },
        {
          "CreateTime": 5,
          "FinishTime": 5,
          "Progress": 8,
          "Status": "jadthNuI",
          "Url": "dehdHOoC"
        },
        {
          "CreateTime": 4,
          "FinishTime": 5,
          "Progress": 9,
          "Status": "KCTmUkpl",
          "Url": "UxQiBarm"
        }
      ]
    },
    {
      "CreateTime": 3,
      "Status": "xRRNKppD",
      "TaskId": "YLQhYqyq",
      "UrlLists": [
        {
          "CreateTime": 8,
          "FinishTime": 5,
          "Progress": 3,
          "Status": "qhlDmXYg",
          "Url": "fJbCCejm"
        },
        {
          "CreateTime": 8,
          "FinishTime": 4,
          "Progress": 4,
          "Status": "IViYWdSq",
          "Url": "LkEYimIs"
        },
        {
          "CreateTime": 2,
          "FinishTime": 1,
          "Progress": 7,
          "Status": "uCbnQqLo",
          "Url": "NbtQArje"
        },
        {
          "CreateTime": 7,
          "FinishTime": 7,
          "Progress": 9,
          "Status": "SHEYNyGf",
          "Url": "ylzrmbHW"
        },
        {
          "CreateTime": 3,
          "FinishTime": 9,
          "Progress": 8,
          "Status": "lgCecoFw",
          "Url": "cYVWknQE"
        },
        {
          "CreateTime": 4,
          "FinishTime": 7,
          "Progress": 1,
          "Status": "JhdorWII",
          "Url": "OEykZxWV"
        },
        {
          "CreateTime": 4,
          "FinishTime": 4,
          "Progress": 1,
          "Status": "GlHxqIgx",
          "Url": "RWWfGzMi"
        }
      ]
    }
  ],
  "Test": "ryEuYMgQ",
  "TotalCount": 4
}
```





