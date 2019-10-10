# 获取成员列表-DescribeMemberList

获取成员列表，限主账号使用。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，请参考[GetProjectList接口](api/summary/get_project_list)。不填写为查询所有项目。|No|
|Offset|string|成员列表的偏移量，默认为0|No|
|Limit|string|成员列表的最大数量，默认为200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|MemberSet|array|JSON格式的成员列表实例|**Yes**|
|TotalCount|int|成员总数|**Yes**|

## MemberInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|MemberEmail|string|成员邮箱|**Yes**|
|MemberPhone|string|成员手机|**Yes**|
|MemberName|string|成员名字|**Yes**|
|MemberPosition|string|成员地址|**Yes**|
|MemberQQ|string|成员QQ|**Yes**|
|PublicKey|string|公钥|**Yes**|
|LastRegionId|string|最后访问的机房|**Yes**|
|DefultProjectId|string|默认项目|**Yes**|
|LastLogin|int|最后一次登录时间|**Yes**|
|Created|int|创建时间|**Yes**|
|State|string|状态|**Yes**|
|IsAdmin|int|是否主账号（0：子账号，1：主账号）|**Yes**|
|IsFinance|int|是否有财务权限（0：无财务权限，1：有财务权限）|**Yes**|
|ProjectSet|array|项目列表|**Yes**|
|ActivateFlag|int|激活状态（0：未激活，1：已激活）|**Yes**|
|PasswordPolicyDate|int|密码安全策略开启时间，格式：unix timestamp|**Yes**|
|TOTPStatus|int|TOTP状态（0：未开启，1：已开启）|**Yes**|
|MandatoryTOTP|int|是否强制开启TOTP （0：否，1：是）|**Yes**|

## ProjectInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectName|string||**Yes**|
|ProjectId|string||**Yes**|
|CharacterId|string||**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeMemberList
&ProjectId=gVhmRqSF
&Offset=0
&Limit=10
```

# Response Example
```
{
    "Action": "DescribeMemberListResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "MemberSet": [
        {
            "MemberQQ": "BHow3", 
            "MemberPosition": "lBHo2", 
            "IsFinance": 0, 
            "PublicKey": "BLihwFHoiyo24ihyLIBHFOIWRgho24yosihdlh+=", 
            "MemberName": "LGwo4hy", 
            "ProjectSet": [
                {
                    "ProjectId": "fzzfcBg1", 
                    "CharacterId": "Lbhi2bw", 
                    "ProjectName": "gejaE45"
                }
            ], 
            "Created": 1524125597, 
            "IsAdmin": 1, 
            "LastRegionId": "cn-east-04", 
            "MemberEmail": "test1@ucloud.cn", 
            "State": "Normal", 
            "ActivateFlag": 1, 
            "LastLogin": 0, 
            "DefultProjectId": "bjwoig", 
            "PasswordPolicyDate": 0, 
            "MemberPhone": "(86)12345678901", 
            "TOTPStatus": 0
        }, 
        {
            "MemberQQ": "BHJowf", 
            "MemberPosition": "LBho2", 
            "IsFinance": 0, 
            "PublicKey": "xLihwFHoiyo114gyLBWOHFOIWRgho24yosi23dl42BSk", 
            "MemberName": "xnwo33y", 
            "ProjectSet": [
                {
                    "ProjectId": "BHOWIlgho", 
                    "CharacterId": "gwhoeigh", 
                    "ProjectName": "woihgoBH"
                }
            ], 
            "Created": 1524125597, 
            "IsAdmin": 1, 
            "LastRegionId": "cn-east-03", 
            "MemberEmail": "test2@ucloud.cn", 
            "State": "Normal", 
            "ActivateFlag": 1, 
            "LastLogin": 0, 
            "DefultProjectId": "Bliwhe", 
            "PasswordPolicyDate": 0, 
            "MemberPhone": "(86)12345678902", 
            "TOTPStatus": 0
        }
    ]
}
```

