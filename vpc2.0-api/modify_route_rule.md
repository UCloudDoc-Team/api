# 路由策略增、删、改-ModifyRouteRule

路由策略增、删、改

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|RouteTableId|string|通过DescribeRouteTable拿到|**Yes**|
|RouteRule.n|string|格式: RouteRuleId \| 目的网段 \| 下一跳类型（支持INSTANCE、VIP） \| 下一跳 \|优先级（保留字段，填写0即可）\| 备注 \| 增、删、改标志（add/delete/update） 。"添加"示例: test_id \| 10.8.0.0/16 \| instance \| uhost-xd8ja \| 0 \| Default Route Rule\| add (添加的RouteRuleId填任意非空字符串) 。"删除"示例: routerule-xk3jxa \| 10.8.0.0/16 \| instance \| uhost-xd8ja \| 0 \| Default Route Rule\| delete (RouteRuleId来自DescribeRouteTable中)     。“修改”示例: routerule-xk3jxa \| 10.8.0.0/16 \| instance \| uhost-cjksa2 \| 0 \| Default Route Rule\| update (RouteRuleId来自DescribeRouteTable中)   |**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyRouteRule
&ProjectId=org-test
&Region=cn-bj2
&RouteTableId=routetable-34kjhfdsakhfds
&RouteRule.0=routeruleId|172.168.8/24|vip|vip-kjs8sJ|0|test|add
```

# Response Example
```
{
    "Action": "ModifyRouteRuleResponse", 
    "RetCode": 0
}
```

