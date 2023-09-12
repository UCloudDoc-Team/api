# 更新负载均衡实例属性 - UpdateLoadBalancerAttribute

## 简介

更新一个应用型负载均衡实例或者一个网络型负载均衡实例的属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateLoadBalancerAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateLoadBalancerAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **Name** | string | 名字，不传则默认不修改 |No|
| **Tag** | string | 负载均衡实例所属的业务组ID，不传则默认不修改； 传空则为Default业务组 |No|
| **Remark** | string | 负载均衡实例的备注信息，不传则默认不修改，限定字符长度：[0-255] |No|
| **AccessLogConfig** | [*AccessLogConfig*](#AccessLogConfig) | （应用型专用）访问日志相关配置，不传则默认不修改。具体结构详见 AccessLogConfig |No|

#### 数据模型


#### AccessLogConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | bool | 应用型专用）是否开启访问日志记录功能； 不传则默认不修改 |No|
| **US3BucketName** | string | （应用型专用）用于存储访问日志的bucket； 开启日志功能时必传； 修改日志时不传或传空则默认不修改 |No|
| **US3TokenId** | string | （应用型专用）上传访问日志到bucket所需的token； 开启日志功能时必传； 修改日志时不传或传空则默认不修改 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```json
curl 'https://api.ucloud.cn' \
--header 'Content-Type: application/json' \
--data '{
  "Action": "UpdateLoadBalancerAttribute",
  "Region": "cn-bj2",
  "ProjectId": "project-XXXXX",
  "LoadBalancerId": "alb-XXXXX",
  "Name": "albName",
  "Tag": "albTag",
  "Remark": "albRemark",
  "AccessLogConfig": {
    "Enabled": true,
    "US3BucketName": "alb_log",
    "US3TokenId": "xxx-xxx-xxx-xxx-xxx"
  }
}'
```

### 响应示例
    
```json
{
  "Action": "UpdateLoadBalancerAttributeResponse",
  "RetCode": 0
}
```





