# 批量更新CLB的后端实例属性 - UpdateBackendBatch

## 简介

批量更新CLB后端资源实例(服务节点)属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateBackendBatch)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateBackendBatch`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 传统型负载均衡实例ID |**Yes**|
| **Attributes** | array[[*AttributeSet*](#AttributeSet)] | 要修改的传统型负载均衡服务节点信息。具体结构详见 AttributeSet |**Yes**|

#### 数据模型


#### AttributeSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackendId** | string | 后端资源实例的ID(CLB后端节点ID，非资源自身ID)。 |**Yes**|
| **Weight** | int | 所添加的后端RS权重（在加权轮询算法下有效）。取值范围[1-100]；如果该节点属于主备算法的vserver，则不会修改Weight；不传该参数则默认不修改 |No|
| **Port** | int | 后端资源服务端口。取值范围[1-65535]；报文转发型负载均衡不允许修改端口；不传该参数则默认不修改 |No|
| **Enabled** | bool | 后端实例状态开关。如果该节点属于主备算法的vserver，则不会修改Enabled；不传该参数则默认不修改 |No|
| **IsBackup** | bool | 服务节点是否为备节点， 0：主rs 1：备rs。 只有该服务节点所属的vserver是主备算法才会修改主备属性；不传该参数则默认不修改 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackendSet** | array[[*BackendMsg*](#BackendMsg)] | 返回clb对每个rs的修改是否成功。具体结构见下方 BackendMsg |No|

#### 数据模型


#### BackendMsg

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackendId** | string | rs的资源ID |**Yes**|
| **SubMessage** | string | 修改rs返回的消息 |**Yes**|
| **SubRetCode** | int | 修改rs是否成功的返回值 |**Yes**|




## 示例

### 请求示例
    
```json
curl 'https://api.ucloud.cn' \
--header 'Content-Type: application/json' \
--data '{
    "Action": "UpdateBackendBatch",
    "Region": "cn-bj2",
    "ProjectId": "org-XXXXX",
    "ULBId": "ulb-XXXXX",
    "Attributes": [
        {
            "BackendId": "backend-XXXXX",
            "Port": 80,
            "Weight": 1,
            "Enabled": 1,
            "IsBackup": 0
        }
    ]
}'
```

### 响应示例
    
```json
{
  "Action": "UpdateBackendBatchResponse",
  "BackendSet": [
        {
            "BackendId": "backend-XXXXX",
            "SubMessage": "success",
            "SubRetCode": 0
        }
    ],
  "RetCode": 0
}
```





