# 获取项目 ID

项目是 UCloud 的资源的拥有者，通常情况下，项目之间资源是独立的，不互通。UCloud 大部分资源都支持根据 ProjectId 来查询

## 快速查询

<!-- tabs:start -->

#### ** CURL **

?> 通过 CURL 发起请求需要手动计算签名，签名计算方法请参考 [签名算法](https://docs.ucloud.cn/api/summary/signature)。

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{
    "Action":"GetProjectList",
    "IsFinance":"Yes",
    "PublicKey":"...",
    "Signature":"..."
  }'
```

!> 建议使用 CLI/SDK/UAPI 等工具发起查询，无需关心签名参数等问题。

#### ** CLI **

**安装**

```bash
brew install ucloud
ucloud init
```

?> 按照提示输入密钥信息，密钥信息可以从 [此页面](https://console.ucloud.cn/uapi/apikey) 获取。

**查询**

```bash
ucloud project list
```

#### ** SDK **

**安装**

```bash
pip install ucloud-sdk-python3
```

**查询**

```python
from ucloud.client import Client

client = Client({"public_key": "...", "private_key": "..."})
client.uaccount().get_project_list()
```

?> 请将代码片段中的 key 替换为自己的公私钥，密钥信息可以从 [此页面](https://console.ucloud.cn/uapi/apikey) 获取。

#### ** UAPI **

访问 [UAPI](https://console.ucloud.cn/uapi/detail?id=GetProjectList) 查询

<!-- tabs:end -->

## 附录

### GetProjectList

获取项目列表

#### Request Parameters

|Parameter name|Type |Description |Required|
|---|---|---|---|
|IsFinance   |string|是否有财务权限，YES：有，NO：没有|No      |

#### Response Elements

|Name        |Type   |Description                       |
|---|---|---|
|Action      |String |响应动作: GetProjectListResponse      |
|RetCode     |Integer|执行成功与否，0表示成功，其他值则为错误代码            |
|ProjectSet  |Array  |JSON格式的项目列表实例，每项参数参见下面的 ProjectSet|
|ProjectCount|Integer|项目总数                              |

**模型定义**：`ProjectSet`

|Name         |Type   |Description  |
|---|---|---|
|ProjectId    |Integer|项目ID         |
|ProjectName  |String |项目名称         |
|ParentId|string|父项目ID|
|ParentName|string|父项目名称|
|CreateTime   |Integer|创建时间(Unix时间戳)|
|IsDefault    |Bool   |是否为默认项目      |
|ResourceCount|Integer|项目下资源数量      |
|MemberCount  |Integer|项目下成员数量      |


#### Request Example

```
https://api.ucloud.cn/?Action=GetProjectList
&IsFinance=Yes
```

#### Response Example

```
{
  "Action": "GetProjectListResponse",
  "ProjectCount": 2,
  "ProjectSet": [
    {
      "ProjectId": "org-1",
      "ProjectName": "ucloud",
      "ParentId": "",
      "ParentName": "",
      "CreateTime": 1342434682,
      "IsDefault": true,
      "MemberCount": 1,
      "ResourceCount": 52
    },
    {
      "ProjectId": "org-2",
      "ProjectName": "test",
      "ParentId": "",
      "ParentName": "",
      "CreateTime": 1468225814,
      "IsDefault": false,
      "MemberCount": 0,
      "ResourceCount": 10
    }
  ],
  "RetCode": 0
}
```
