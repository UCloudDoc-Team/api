# API 文档综览

本文档是 UCloud 云计算产品 API 参考手册。在本文档中，您能够获取到对于每一个指令的描述，语法以及使用示例。
您可以通过用 HTTP/HTTPS GET 的方式对我们的 API 进行调用，或选择适合您所使用编程语言的 SDK 来访问我们的 API。
在调用 API 时，除了需要给出相应的 API 调用地址，公共参数，API 指令，以及指令参数之外，您还需要在调用请求中给出 API 密钥进行身份认证，请您务必妥善保管好您的 API 密钥。

## API 请求结构

| Name      |Description                           |Notes                               |
|---|---|---|
| API调用地址  | 调用API的webservice入口                    | http(s)://api.ucloud.cn         |
| 公共参数     | 调用API时需要给出的公共参数                       | 参见 [公共参数列表](api/summary/public)  |
| API指令    | 即API指令名称，如 **DescribeUhostInstance**  | 参见 [API指令列表](api/index)                |
| 指令参数     | 执行每个指令时所需要提供的参数                       | 参见 [API指令列表](api/index)                |

## API 请求示例

<!-- tabs:start -->

#### ** CURL **

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{
    "Action":"DescribeUHostInstance",
    "PublicKey":"SI3zdT8g1tMInvahPNkckt3Ul8Pq+krxm+yT8MSK7Sd81nWxFOKxdw==",
    "Region":"hk",
    "Signature":"ed5ccd667678292a08dae1828710b4ef4bb57085",
    "ProjectId":"org-e15e0x"
}'
```

### 参数拼接方式

下面是一个API请求示例，所调用的是DescribeUHostInstance指令。

```
http(s)://api.ucloud.cn/?Action=DescribeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostIds.0=uhost-qs20fr
&Offset=0
&Limit=20  
&PublicKey=ucloudsomeone@example.com1296235120854146120
&Signature=2697152c34abbc148a38a33c0dc0d3d7b99ce82f
```

<!-- tabs:end -->

!> 请使用您的 PublicKey 与 Signature 参数值替换这里的参数值。

## API 返回结构

| Name    | Description                                                       | Notes                                   |
|---|---|---|
| 指令名称    | 返回所调用的指令名称。 例如 DescribeUHostInstanceResponse                      | API 返回的指令名称为 "API 指令名称"+"Response" 来表示。  |
| API返回码  | 用来表示 API 请求的返回值 ，当 ret_code = 0 时表示 API 请求正常， ret_code != 0 时表示 API 请求错误。  |                                         |
| 返回参数    | 每个 API 的返回参数                                                        | 参见 [API指令列表](api/index)                   |

## API 返回示例

该 API 的返回值为如下所示的 JSON 格式内容。

```javascript
{
     "Action" : "DescribeUHostInstanceResponse",
     "TotalCount" : 1,
     "RetCode" : 0,
     "UHostSet" : [
         {
             "UHostId":"uhost-qs20fr",
             "ImageId": "ee51e7ba-7b48-4332-b6e8-990bd56f81af",
             "BasicImageId": "08d3b48b-ba14-4b1a-a5dd-cbacf8b820f2",
             "BasicImageName": "Ubuntu 10.04 64位",
             "Tag":"tag-test",
             "Name":"name-test",
             "Remark":"remark-test",
             "State":"Running",
             "CreateTime":1234567890,
             "ChargeType":"Dynamic",
             "ExpireTime":1398328902,
             "CPU":2,
             "Memory":2048,
             "AutoRenew":"Yes",
             "NetworkState": "Connected",
             "NetCapability":"Yes",
             "AutoRenew": "Yes",
             "DiskSet":[
                 {
                     "Type": "Boot",
                     "DIskId": "209883a7-aaee-4492-974d-5d9d64ef79c4",
                     "Drive": "/dev/sda",
                     "Size": 20
                 },
                 {
                     "Type": "Data",
                     "DIskId": "5daef46a-63e6-40c2-8d0a-d3d5b3bc4d5b",
                     "Drive": "/dev/sdb",
                     "Size": 40
                 },
                 {
                     "Type": "Udisk",
                     "DIskId": "ce8a9f2a-28c7-4267-8cff-eafb714e3b18",
                     "Drive": "/dev/sdc",
                     "Size": 100
                 }
             ],
             "IpSet": [
                 {
                     "Type": " Private ",
                     "IP":"10.6.6.1"
                 },
                 {
                     "Type":" Bgp ",
                     "IPId":"cc9732a6-d43a-45ca-b867-fb90052ffe88",
                     "IP": "118.192.72.21",
                     "Bandwidth": 2
                 }
             ]
         }
     ]
 }
```
