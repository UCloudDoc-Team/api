# API 索引

## ALB

| API | 描述信息 |
|:---|:---|
|[CreateLoadBalancer](api/ulb-api/create_load_balancer)|创建应用型负载均衡实例|
|[CreateListener](api/ulb-api/create_listener)|创建应用型负载均衡监听器|
|[AddTargets](api/ulb-api/add_targets)|添加应用型负载均衡的后端服务节点|
|[CreateRule](api/ulb-api/create_rule)|创建应用型负载均衡的转发规则|
|[DeleteLoadBalancer](api/ulb-api/delete_load_balancer)|删除应用型负载均衡实例|
|[DeleteListener](api/ulb-api/delete_listener)|删除应用型负载均衡监听器|
|[RemoveTargets](api/ulb-api/remove_targets)|删除应用型负载均衡的后端服务节点|
|[DeleteRule](api/ulb-api/delete_rule)|删除应用型负载均衡的转发规则|
|[UpdateLoadBalancerAttribute](api/ulb-api/update_load_balancer_attribute)|更新应用型负载均衡实例属性|
|[UpdateListenerAttribute](api/ulb-api/update_listener_attribute)|更新应用型负载均衡监听器属性|
|[UpdateTargetsAttribute](api/ulb-api/update_targets_attribute)|更新应用型负载均衡的后端服务节点属性|
|[UpdateRuleAttribute](api/ulb-api/update_rule_attribute)|更新应用型负载均衡的转发规则属性|
|[DescribeLoadBalancers](api/ulb-api/describe_load_balancers)|描述应用型负载均衡实例|
|[DescribeListeners](api/ulb-api/describe_listeners)|描述应用型负载均衡监听器|
|[DescribeRules](api/ulb-api/describe_rules)|描述应用型负载均衡转发规则|

## CLB

| API | 描述信息 |
|:---|:---|
|[CreateULB](api/ulb-api/create_ulb)|创建传统型负载均衡负载均衡|
|[CreateVServer](api/ulb-api/create_vserver)|创建CLB的VServer|
|[BindSSL](api/ulb-api/bind_ssl)|传统型负载均衡绑定SSL证书|
|[AllocateBackend](api/ulb-api/allocate_backend)|添加传统型负载均衡的后端实例|
|[CreatePolicy](api/ulb-api/create_policy)|传统型负载均衡创建内容转发策略|
|[DeleteULB](api/ulb-api/delete_ulb)|删除传统型负载均衡|
|[DeleteVServer](api/ulb-api/delete_vserver)|删除CLB的VServer|
|[ReleaseBackend](api/ulb-api/release_backend)|释放传统型负载均衡的后端实例|
|[UnbindSSL](api/ulb-api/unbind_ssl)|传统型负载均衡解绑SSL证书|
|[DeletePolicy](api/ulb-api/delete_policy)|删除传统型负载均衡的内容转发策略|
|[UpdateULBAttribute](api/ulb-api/update_ulb_attribute)|更新传统型负载均衡属性|
|[UpdateVServerAttribute](api/ulb-api/update_vserver_attribute)|更新传统型负载均衡VServer属性|
|[UpdateBackendAttribute](api/ulb-api/update_backend_attribute)|更新传统型负载均衡的后端实例属性|
|[UpdateBackendBatch](api/ulb-api/update_backend_batch)|批量更新后端实例属性|
|[UpdatePolicy](api/ulb-api/update_policy)|更新传统型负载均衡内容转发规则|
|[DescribeULB](api/ulb-api/describe_ulb)|获取传统型负载均衡信息|
|[DescribeULBSimple](api/ulb-api/describe_ulb_simple)|获取传统型负载均衡信息|
|[DescribeVServer](api/ulb-api/describe_vserver)|获取CLB下的VServer信息|
|[DescribeSSL](api/ulb-api/describe_ssl)|获取SSL证书信息|
|[DescribeSecurityPolicies](api/ulb-api/describe_security_policies)|获取安全策略的信息|

## 公共 API

| API | 描述信息 |
|:---|:---|
|[CreateSSL](api/ulb-api/create_ssl)|创建SSL证书|
|[DeleteSSL](api/ulb-api/delete_ssl)|删除SSL证书|
|[UpdateSSLAttribute](api/ulb-api/update_ssl_attribute)|更新SSL属性|
|[UpdateSSLBinding](api/ulb-api/update_ssl_binding)|更换证书绑定关系|
|[DescribeSSLV2](api/ulb-api/describe_sslv2)|获取SSL证书信息|
|[DescribeSupportCiphers](api/ulb-api/describe_support_ciphers)|描述支持的加密套件|
|[UpdateSecurityPolicy](api/ulb-api/update_security_policy)|更新安全策略|
|[CreateSecurityPolicy](api/ulb-api/create_security_policy)|创建安全策略|
|[DeleteSecurityPolicy](api/ulb-api/delete_security_policy)|删除安全策略|
|[UnBindSecurityPolicy](api/ulb-api/un_bind_security_policy)|解绑安全策略|
|[DescribeSecurityPoliciesV2](api/ulb-api/describe_security_policies_v2)|获取安全策略的信息|
|[AddSSLBinding](api/ulb-api/add_ssl_binding)|新增监听器绑定证书|
|[DeleteSSLBinding](api/ulb-api/delete_ssl_binding)|删除监听器绑定的扩展证书|
