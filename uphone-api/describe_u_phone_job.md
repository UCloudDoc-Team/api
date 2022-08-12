# 查询Job的执行状态。 - DescribeUPhoneJob

## 简介

查询Job的执行状态。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPhoneJob`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |No|
| **JobIds.N** | string | 【数组】Job 的唯一标识 Id，调用方式举例：JobIds.0=希望查询状态的 Job1，JobIds.1=Job2。 如果不传入，则返回当前 城市 所有符合条件的 Job 。 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **State** | string | Job状态，枚举值：<br />* 等待状态: PENDING;<br />* 运行状态: RUNNING;<br />* 成功状态: SUCCESS<br />* 失败状态: FAILED<br />* 部分成功状态：PARTIAL_SUCCESS |No|
| **Types.N** | string | 【数组】Job 类型，调用方式举例：JobTypes.0=希望查询的 Job 类型 1，JobTypes.1=Job 类型 2。 如果不传入，则返回当前 城市 所有符合条件的 Job 类型。Job 类型仅支持 INSTALL_APP、UNINSTALL_APP、RUN_ASYNC_COMMAND、CREATE_SERVER_AND_UPHONE、SET_UPHONE_GPS、SET_UPHONE_CONFIG、UPLOAD_FILE、DELETE_UPHONE |No|
| **ProductType** | string | 枚举值。当前操作的产品类型，1、uphone：云手机场景；2、uphone-server：云手机服务器场景。默认云手机服务器场景。<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Jobs** | array[[*Job*](#Job)] | Job信息，详情见数据结构Job（如果Status为等待中，此字段为空）	 |No|
| **TotalCount** | int | Job总数 |No|

#### 数据模型


#### Job

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **JobId** | string | Job的唯一标识Id	 |No|
| **CreateTime** | int | Job创建时间，格式为Unix时间戳。	 |No|
| **BeginTime** | int | Job处理开始时间，格式为Unix时间戳。	 |No|
| **EndTime** | int | Job处理结束时间，格式为Unix时间戳。	 |No|
| **State** | string | 任务状态<br />* 等待中：PENDING<br />* 运行中：RUNNING<br />* 成功：SUCCESS<br />* 部分成功：PARTIAL_SUCCESS<br />* 失败：FAILED |No|
| **JobType** | string | Job类型，仅支持INSTALL_APP、UNINSTALL_APP、RUN_ASYNC_COMMAND。 |No|
| **Tasks** | array[[*Task*](#Task)] | Task信息，详情见数据结构Task（如果State为PENDING，此字段为空）	 |No|
| **AppVersionId** | string | 安装/卸载Job相关的应用版本唯一标识 |No|
| **UPhoneIds** | array[string] | 此Job相关的云手机唯一标识 |No|

#### Task

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TaskId** | string | Task的唯一标识	 |**Yes**|
| **BeginTime** | int | 任务处理开始时间，格式为Unix时间戳。	 |**Yes**|
| **EndTime** | int | 任务处理结束时间，格式为Unix时间戳。	 |**Yes**|
| **State** | string | 任务状态<br />* 等待中：PENDING<br />* 运行中：RUNNING<br />* 成功：SUCCESS<br />* 失败：FAILED |**Yes**|
| **ErrorMsg** | string | Task错误信息 |**Yes**|
| **ExecuteMsg** | string | 异步任务执行结果 |No|
| **UPhoneId** | string | 云手机的唯一标识，云手机相关任务包含此字段。	 |No|
| **AppVersionId** | string | 安装/卸载任务相关的应用版本唯一标识ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPhoneJob
&Region=cn-zj
&ProjectId=mriUzdxM
&JobIds.N=NPsAGnbJ
&JobStatus=BBCNLDXM
&JobType=uPxbavrf
&Offset=8
&Limit=7
&CityId=ZXenAKca
&ProductType=XvENrhMO
```

### 响应示例
    
```json
{
  "Action": "DescribeUPhoneJobResponse",
  "BeginTime": "qamMsYcQ",
  "EndTime": "YasvKGQq",
  "JobId": "GQNSsiqb",
  "Jobs": [
    {
      "BeginTime": "SLNnpmiZ",
      "EndTime": "ussLnLoG",
      "JobId": "zQKKGIvY",
      "JobType": "JKcxNKid",
      "State": "GuswRaNJ",
      "Tasks": [
        {
          "BeginTime": 3,
          "EndTime": 2,
          "ErrorMsg": "rKNGnduI",
          "ExecuteMsg": "NIcaoRJE",
          "ServerId": "PkqDwKRf",
          "State": "JtGjRuJr",
          "TaskId": "wEuIbQqV",
          "UPhoneId": "wTmZznUR"
        }
      ]
    }
  ],
  "Message": "SakOSUlA",
  "RetCode": 0,
  "Status": "eBnyYuFP",
  "Tasks": [
    {
      "BeginTime": "ZPLJGpHz",
      "EndTime": "yBZoJQlL",
      "Message": "iTPexVOX",
      "PhoneId": "jlVyhqMG",
      "ServerId": "MEIYlUch",
      "Status": "TGzuccHj",
      "TaskId": "TgUwlack"
    }
  ],
  "TotalCount": 7
}
```





