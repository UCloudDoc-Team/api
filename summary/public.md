# 公共参数

公共参数是在操作所有 API 的时候，都必需给出的参数。

!> 为避免重复，下列公共参数不会再在各 API 文档中列出。

## 公共参数列表

| 参数名      | 必选     |参数类型    | 说明                                                   |
|---|---|---|---|
| Action     | true   | String  | 对应的 API 名称，如 CreateUHostInstance                        |
| PublicKey  | true   | String  | 用户公钥                                                 |
| Signature  | true   | String  | 根据公钥及API指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  |
| ProjectId  | false  | String  | 项目 ID，主账号与财务账号为空时为默认项目；子账号为必填字段    |
