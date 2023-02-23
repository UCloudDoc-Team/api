# 解冻文件 - Restore 


## 简介
解冻文件

## 解冻过程说明

对于归档类型的Object，如果需要读取Object，请提前解冻。归档类型Object根据不同解冻优先级，解冻完成时间不同，请以实际解冻时间为准。

归档类型或者冷归档类型的Object在执行解冻前后的状态变换过程如下:

1. Object初始时处于归档状态。
2. 提交一次解冻请求后，Object处于解冻中状态。
3. 服务端完成解冻任务后，Object进入解冻状态，此时您可以读取Object。您可以指定解冻优先级，不同解冻优先级的首字节取回时间如下：
   * 高优先级（Expedited）：表示15分钟内完成。
   * 标准（Standard）：表示1~5小时内完成。如果不传入解冻类型，则默认为Standard。
4. 解冻状态结束后，Object再次返回到归档状态。

Requests

Syntax:

```
PUT /<object_name>?restore HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```
### 请求参数（Request Parameters）


**请求头（Request Headers）**

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|解冻请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |Yes     |


**请求元素（Request Elements）**

> 说明：未使用


### 响应（Responses）


**响应头（Response Headers）**

| Name          | Type   | Description                                                  | Required |
| ------------- | ------ | ------------------------------------------------------------ | -------- |
| Authorization | String | 解冻请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95) | Yes      |
| Tier          | String | 归档文件解冻优先级。<br>取值如下：<br>* Expedited（高优先级）：15分钟内解冻完成。<br>* Standard（标准，默认值）：1~5小时完成解冻。 | No       |

**响应元素（Response Elements）**

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误码  |
|ErrMsg |String |执行失败时的错误消息 |

> 注意: 成功执行只会返回HTTP 200回应,不带body数据.

## 示例

### 请求示例（Example Request）:

```
PUT /archive_file.txt?restore HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```

### 响应示例（Example Response）:

```
HTTP/1.1 200 OK
Content-Length: 0
```

