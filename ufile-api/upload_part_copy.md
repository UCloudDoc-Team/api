# 拷贝分片 - UploadPartCopy

## 简介

通过在UploadPart请求的基础上增加一个请求头 `X-Ufile-Copy-Source` 来调用UploadPartCopy接口，实现从一个已存在的Object中拷贝数据来上传一个Part。

## **注意事项**

当拷贝一个大于100 MB的文件时，必须使用UploadPartCopy的方式进行拷贝。如果想通过单个操作拷贝小于100 MB的文件，请参见[CopyObject](https://docs.ucloud.cn/api/ufile-api/copy)。

使用UploadPartCopy接口时，有如下注意事项：

- 执行UploadPartCopy的源Bucket地址和目标Bucket地址必须是同一个Region。
- 调用该接口上传Part数据前，必须先调用InitiateMultipartUpload接口来获取一个US3服务器颁发的Upload ID。
- MultipartUpload要求除最后一个Part以外，其他的Part大小都要等于4 MB。因不确定是否为最后一个Part，UploadPart/UploaderPartCopy接口并不会立即校验上传Part的大小，只有当CompleteMultipartUpload的时候才会校验。

## 定义

### ****句法（Syntax）:****

```jsx
PUT /<object_name>?uploadId=<upload_id>&partNumber=<part_number> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Type: <mimetype>
Content-Length: <length>
X-Ufile-Copy-Source: /SourceBucketName/SourceObjectName
X-Ufile-Copy-Source-Range: bytes=first-last
```

### **请求参数（Request Parameters）**

**请求头（Request Headers）**

| Name                      | Type   | Description                                                  | Required |
| ------------------------- | ------ | ------------------------------------------------------------ | -------- |
| Authorization             | String | 上传请求的授权签名，https://docs.ucloud.cn/ufile/api/authorization?id=文件管理签名算法 | Yes      |
| X-Ufile-Copy-Source       | String | 指定拷贝的源地址，默认值：无                                 | Yes      |
| X-Ufile-Copy-Source-Range | int    | 源Object的拷贝范围。例如设置bytes=0 ~ 9，表示拷贝0到9这10个字符。<br>* 当指定该请求头时，则返回消息中会包含整个文件的长度和此次拷贝的范围，例如：Content-Range: bytes 0 ~ 9/44，表示整个文件长度为44，此次拷贝的范围为0 ~ 9。<br>* 当指定的范围不符合规范时，返回419。 | Yes      |


**请求元素（Request Elements）**

> 说明：未使用。
> 

### **响应（Responses）**

**响应头（Response Headers）**

| Name | Type | Description |
| --- | --- | --- |
| ETag | String | 已经上传文件在US3中的哈希值 |
| X-SessionId | String | 请求失败时返回本次请求的会话Id |

**响应元素（Response Elements）**

| Name | Type | Description |
| --- | --- | --- |
| PartNumber | Integer | 本次分片上传的分片号码 |

# **示例**

### **请求示例（Example Request）:**

```
PUT /demokey?uploadId=0f188eb2-5e19-49c3-94c9-36fb5a0ff72a&partNumber=0 HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
X-Ufile-Copy-Source: /bucket-us3-test/object-us3
X-Ufile-Copy-Source-Range: bytes=0-4194303
```

### **响应示例（Example Response）:**

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 4194304
ETag: "AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH"
Content-Range: bytes 0-4194303/5194303

{
   "PartNumber": 0
}
```
