# 导入配置 - UploadUDBParamGroup

## 简介

导入UDB配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UploadUDBParamGroup)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UploadUDBParamGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **DBTypeId** | string | DB类型id，DB类型id，mysql/mongodb/postgesql按版本细分 1：mysql-5.1，2：mysql-5.5，3：percona-5.5，4：mysql-5.6，5：percona-5.6，6：mysql-5.7，7：percona-5.7，8：mariadb-10.0，9：mongodb-2.4，10：mongodb-2.6，11：mongodb-3.0，12：mongodb-3.2,13：postgresql-9.4，14：postgresql-9.6 |**Yes**|
| **GroupName** | string | 配置参数组名称 |**Yes**|
| **Description** | string | 参数组描述 |**Yes**|
| **Content** | string | 配置内容，导入的配置内容采用base64编码 |**Yes**|
| **RegionFlag** | boolean | 该配置文件是否是地域级别配置文件，<br />默认是false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupId** | int | 配置参数组id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UploadUDBParamGroup     
&Region=cn-bj2
&Zone=cn-bj2-04
&DBTypeId=mysql-5.1
&GroupName=mysql-xxx-config
&Description=xxx-config                   
&Content=W2NsaWVudF0NCiBwb3J0ID0gMzMwNg0KIHNvY2tldCA9IC90bXAvbXlzcWwuc29jaw0KIFtteWlzYW1jaGtdDQoga2V5X2J1ZmZlcl9zaXplID0gMjBNDQogcmVhZF9idWZmZXIgPSAyTQ0KIHNvcnRfYnVmZmVyX3NpemUgPSAyME0NCiB3cml0ZV9idWZmZXIgPSAyTQ0KIFtteXNxbF0NCiBuby1hdXRvLXJlaGFzaA0KIFtteXNxbGRdDQogYmFja19sb2cgPSAyMDAwDQogYmFzZWRpciA9IC9vcHQvdWRiL3Byb2dyYW0vbXlzcWwvbXlzcWwtNS42LjIwDQogYmluZC1hZGRyZXNzID0gMTAuNC40LjE2OA0KIGJpbmxvZy1mb3JtYXQgPSBNSVhFRA0KIGNoYXJhY3Rlcl9zZXRfc2VydmVyID0gdXRmOA0KIGRhdGFkaXIgPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL2RhdGENCiBldmVudF9zY2hlZHVsZXIgPSBPTg0KIGV4cGlyZV9sb2dzX2RheXMgPSA3DQogZ2VuZXJhbC1sb2ctZmlsZSA9IC9vcHQvdWRiL2luc3RhbmNlL215c3FsLTUuNi8xN2UzNGY2OS04NGRmLTRkZmUtOTMxOC00ZjVhNWQ4MjQ0NzIvbG9nL215c3FsZC5sb2cNCiBpbm5vZGJfYnVmZmVyX3Bvb2xfc2l6ZSA9IDYyOTE0NTYwMA0KIGlubm9kYl9kYXRhX2ZpbGVfcGF0aCA9IGliZGF0YTE6MTAwTTphdXRvZXh0ZW5kDQogaW5ub2RiX2RhdGFfaG9tZV9kaXIgPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL2RhdGENCiBpbm5vZGJfZmlsZV9wZXJfdGFibGUgPSAxDQogaW5ub2RiX2ZsdXNoX2xvZ19hdF90cnhfY29tbWl0ID0gMg0KIGlubm9kYl9mbHVzaF9tZXRob2QgPSBPX0RJUkVDVA0KIGlubm9kYl9pb19jYXBhY2l0eSA9IDIwMDANCiBpbm5vZGJfbG9nX2J1ZmZlcl9zaXplID0gODM4ODYwOA0KIGlubm9kYl9sb2dfZmlsZV9zaXplID0gNTEyTQ0KIGlubm9kYl9sb2dfZmlsZXNfaW5fZ3JvdXAgPSAyDQogaW5ub2RiX2xvZ19ncm91cF9ob21lX2RpciA9IC9vcHQvdWRiL2luc3RhbmNlL215c3FsLTUuNi8xN2UzNGY2OS04NGRmLTRkZmUtOTMxOC00ZjVhNWQ4MjQ0NzIvZGF0YQ0KIGlubm9kYl9tYXhfZGlydHlfcGFnZXNfcGN0ID0gNTANCiBpbm5vZGJfb3Blbl9maWxlcyA9IDEwMjQNCiBpbm5vZGJfcmVhZF9pb190aHJlYWRzID0gOA0KIGlubm9kYl90aHJlYWRfY29uY3VycmVuY3kgPSAyMA0KIGlubm9kYl93cml0ZV9pb190aHJlYWRzID0gOA0KIGtleV9idWZmZXJfc2l6ZSA9IDMzNTU0NDMyDQogbG9jYWxfaW5maWxlID0gMA0KIGxvZy1iaW4gPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL2JpbmxvZy9teXNxbC1iaW4ubG9nDQogbG9nLWVycm9yID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi9sb2cvbXlzcWxkLmxvZw0KbG9nX2Jpbl90cnVzdF9mdW5jdGlvbl9jcmVhdG9ycyA9IDENCiBsb2dfb3V0cHV0ID0gVEFCTEUNCiBsb25nX3F1ZXJ5X3RpbWUgPSAzDQogbWF4X2FsbG93ZWRfcGFja2V0ID0gMTY3NzcyMTYNCiBtYXhfY29ubmVjdF9lcnJvcnMgPSAxMDAwMDAwDQogbWF4X2Nvbm5lY3Rpb25zID0gMjAwMA0KIG15aXNhbV9zb3J0X2J1ZmZlcl9zaXplID0gODM4ODYwOA0KIG5ldF9idWZmZXJfbGVuZ3RoID0gODE5Mg0KIHBpZC1maWxlID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi9teXNxbGQucGlkDQogcG9ydCA9IDMzMDYNCiBxdWVyeV9jYWNoZV9zaXplID0gMTY3NzcyMTYNCiByZWFkX2J1ZmZlcl9zaXplID0gMjYyMTQ0DQogcmVhZF9ybmRfYnVmZmVyX3NpemUgPSA1MjQyODgNCiByZWxheS1sb2cgPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL3JlbGF5bG9nL215c3FsLXJlbGF5LmxvZw0KIHNlY3VyZS1maWxlLXByaXYgPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL3RtcA0KIHNlcnZlci1pZCA9IDE2ODAzNTQ5Ng0KIHNraXAtc2xhdmUtc3RhcnQNCiBza2lwX25hbWVfcmVzb2x2ZQ0KIHNsYXZlLWxvYWQtdG1wZGlyID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi90bXANCiBzbG93LXF1ZXJ5LWxvZy1maWxlID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi9sb2cvbXlzcWwtc2xvdy5sb2cNCiBzbG93X3F1ZXJ5X2xvZyA9IDENCiBzb2NrZXQgPSAvb3B0L3VkYi9pbnN0YW5jZS9teXNxbC01LjYvMTdlMzRmNjktODRkZi00ZGZlLTkzMTgtNGY1YTVkODI0NDcyL215c3FsZC5zb2NrDQogc29ydF9idWZmZXJfc2l6ZSA9IDUyNDI4OA0KIHN5bmNfYmlubG9nID0gMQ0KIHRhYmxlX29wZW5fY2FjaGUgPSAxMjgNCiB0aHJlYWRfY2FjaGVfc2l6ZSA9IDUwDQogdG1wZGlyID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi90bXANCiB1c2VyID0gbXlzcWwNCiBbbXlzcWxkX3NhZmVdDQogbG9nLWVycm9yID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi9sb2cvbXlzcWxkLmxvZw0KIHBpZC1maWxlID0gL29wdC91ZGIvaW5zdGFuY2UvbXlzcWwtNS42LzE3ZTM0ZjY5LTg0ZGYtNGRmZS05MzE4LTRmNWE1ZDgyNDQ3Mi9teXNxbGQucGlkDQogW215c3FsZHVtcF0NCiBtYXhfYWxsb3dlZF9wYWNrZXQgPSAxNk0NCiBxdWljaw0KIFtteXNxbGhvdGNvcHldDQogaW50ZXJhY3RpdmUtdGltZW91dA0KIC9vcHQvdWRiL2luc3RhbmNlL215c3E%3D&DBTypeId=mysql-5.5&Description=test&GroupName=test1222&PublicKey=ucloudpmtest1%40ucloud.cn140474078895539362&Region=cn-east-01&Signature=941092ab104570b68b7d1b0af922b1174a81a50a
```

### 响应示例
    
```json
{
  "Action": "UploadUDBParamGroupResponse",
  "GroupId": 2,
  "RetCode": 0
}
```





