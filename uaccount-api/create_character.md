# 创建角色 - CreateCharacter

## 简介

创建角色

?> 产品列表：云主机 UHOST、物理主机 UPHOST、托管云 UHYBRID、基础网络 UNET、负载均衡 ULB、云数据库 UDB、SSD云硬盘 UDISK、云内存存储 UMEM、对象存储 UFILE、分布式数据处理 UDDP、托管HADOOP集群 UHADOOP、云分发 UCDN、云点播 UVIDEO、基础安全防护 USEC、云数据仓库 UDW、分布式消息系统 UKAFKA、私有专区资源池 UDSET、AI在线服务 UAI、AI训练服务 UAI-TRAINING、云直播 ULIVE、容器服务 UDOCKER、公共镜像库 UHUB、WEB应用防护 UWAF、分布式数据库 UDDB、数据库审计 DBAUDIT、主机入侵检测 UHIDS、容器云 UK8S、密钥管理服务 UKMS、全球动态加速线路 PATHX、Elasticsearch服务 UES



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateCharacter)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCharacter`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CharacterName** | string | 角色名称，不得与现有角色重名 |**Yes**|
| **CharacterDescription** | string | 角色描述 |No|
| **Add.N** | string | 角色对产品的权限(增) |No|
| **Del.N** | string | 角色对产品的权限(删) |No|
| **Mod.N** | string | 角色对产品的权限(改) |No|
| **Get.N** | string | 角色对产品的权限(查) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CharacterId** | string | 角色ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCharacter
&CharacterName=PkUHnfTq
&CharacterDescription=sOLKZcSH
&Add.n=OKlGsPhP
&Del.n=cZzFveLT
&Mod.n=GrixHXoU
&Get.n=nAKRweHk
```

### 响应示例
    
```json
{
  "Action": "CreateCharacterResponse",
  "CharacterId": "WDmuiLnc",
  "RetCode": 0
}
```





