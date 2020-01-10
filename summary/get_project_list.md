# 获取项目ID

## UCloud
## GetProjectList

获取项目列表

## Request Parameters

|Parameter name|Type |Description |Required|
|---|---|---|---|
|IsFinance   |string|是否有财务权限，YES：有，NO：没有|No      |

## Response Elements

|Name        |Type   |Description                       |
|---|---|---|
|Action      |String |响应动作: GetProjectListResponse      |
|RetCode     |Integer|执行成功与否，0表示成功，其他值则为错误代码            |
|ProjectSet  |Array  |JSON格式的项目列表实例，每项参数参见下面的 ProjectSet|
|ProjectCount|Integer|项目总数                              |

### ProjectSet

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


## Request Example

```
https://api.ucloud.cn/?Action=GetProjectList
&IsFinance=Yes
```

## Response Example

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
