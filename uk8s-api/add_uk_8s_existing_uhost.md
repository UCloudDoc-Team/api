# 添加Node节点（已有云主机） - AddUK8SExistingUHost

## 简介

将预先创建好的云主机加入到UK8S集群，需要注意的是，该云主机依然会执行重装系统的操作。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUK8SExistingUHost`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Password** | string | Node节点密码。请遵照[字段规范](api/uhost-api/specification)设定密码。密码需使用base64进行编码，如下：# echo -n Password1 \| base64 |**Yes**|
| **ClusterId** | string | UK8S集群ID。 可从UK8S控制台获取。<br /> |**Yes**|
| **UHostId** | string | 云主机Id，为了保证节点正常运行，该主机配置不得低于2C4G。 |**Yes**|
| **MaxPods** | int | 默认110，生产环境建议小于等于110。 |No|
| **Labels** | string | Node节点标签。key=value形式,多组用”,“隔开，最多5组。 如env=pro,type=game |No|
| **SubnetId** | string | 该云主机所属子网Id。 |No|
| **ImageId** | string | 镜像 Id，不填时后台程序会自动选用一个可用的镜像 Id，支持用户自定义镜像，自定义镜像必须基于基础镜像制作。 |No|
| **DisableSchedule** | boolean | 用于标示添加完节点后是否将节点临时禁用. 传入 "true" 表示禁用,传入其它或不传表示不禁用 |No|
| **UserData** | string | 用户自定义数据。当镜像支持Cloud-init Feature时可填写此字段。注意：1、总数据量大小不超过 16K；2、使用base64编码。 |No|
| **InitScript** | string | 用户自定义Shell脚本。与UserData的区别在于InitScript在节点初始化完毕后才执行，UserData则是云主机初始化时执行。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUK8SExistingUHost
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=dVbiuuWn
&NodeId=UMOVYunk
&Password=yFgKqXEO
&MaxPods=1
&Labels=Zejwkpch
&ClusterId=KOyqQlVA
&ClusterId=JrBEhuxq
&SubnetId=DCsCsHkw
&ImageId=elKgKSHF
&DisableSchedule=dAOelOGX
&UserData=eqDmkTAX
&InitScript=PhwUTXgX
```

### 响应示例
    
```json
{
  "Action": "AddUK8SExistingUHostResponse",
  "Message": "kCwOaEDG",
  "RetCode": 0
}
```





