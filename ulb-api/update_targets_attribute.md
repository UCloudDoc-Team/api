# 更新后端服务节点属性 - UpdateTargetsAttribute

## 简介

更新监听器后端服务节点的属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateTargetsAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateTargetsAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **Targets** | array[[*TargetUpdate*](#TargetUpdate)] | 要添加的服务节点信息。数组长度至少为1； 不超过20个。具体结构详见 TargetUpdate |**Yes**|

#### 数据模型


#### TargetUpdate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Weight** | int | 服务节点的权重。限定取值：[1-100]； 仅在加权轮询算法时有效；不传则默认不修改 |No|
| **Enabled** | bool | 服务节点是否启用。不传则默认不修改 |No|
| **IsBackup** | bool | 服务节点是否为备节点。不传则默认不修改； 只有该target所属的listener时主备算法才允许修改主备属性 |No|
| **Id** | string | 服务节点的标识ID。 |No|

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
    "Action": "UpdateTargetsAttribute",
    "Region": "cn-bj2",
    "ProjectId": "project-XXXXX",
    "LoadBalancerId": "alb-XXXXX",
    "ListenerId": "als-XXXXX",
    "Targets": [
        {
            "ResourceType": "IP",
            "VPCId": "uvnet-XXXXX",
            "Id": "ars-XXXXX",
            "Weight": 5,
            "Enabled": false,
            "IsBackup": true
        }
    ]
}'
```

### 响应示例
    
```json
{
  "Action": "UpdateTargetsAttributeResponse",
  "RetCode": 0
}
```





