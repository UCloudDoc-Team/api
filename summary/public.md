# 快速开始

## 认识 API

UCloud API 采用指令式的风格，每个 API 请求包含一个指令（`Action`）、指令参数和认证信息（`PublicKey`、`Signature`）。

### 公共参数

公共参数是在操作所有 API 的时候，都必需给出的参数，通常会展示在 API 文档所有参数的最上方。

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，例如 `DescribeUHostInstance` | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [UAPI 控制台](https://console.ucloud.cn/uapi/apikey) 获取 | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature)  | **Yes** |

### 通用参数

通用参数是大部分 API 都可能使用到的参数，具有一致的含义，是否需要给出，取决于具体 API 的定义。

| 参数名 | 类型 | 描述信息 |
|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |
| **Zone** | string | 可用区。参见 [地域和可用区列表](api/summary/regionlist) |
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 参见 [获取项目 ID](api/summary/get_project_list) |

### 公共响应

公共响应是所有 API 都统一遵循的响应风格，包括一个指令响应名称（`Action`），识别 API 是否成功的状态码（`RetCode`）以及当遇到错误时，返回的错误提示信息（`Message`）。

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|

### 错误码说明

| RetCode | 描述 |
|:---|:---|
| 130 | API 网关或者认证鉴权服务异常 |
| 150 | 服务目前不可用，我们正在努力恢复中，请稍后重试 |
| 153 | API 请求被限流 |
| 160 | 缺少关键参数Action，请提供完整的参数 |
| 161 | Action 不存在 |
| 170 | 缺少签名 |
| 171 | 签名错误 |
| 172 | 用户不存在 |
| 174 | Token 不存在 |
| 292 | 项目不存在 |
| 293 | 可用区权限错误 |
| 294 | 访问IP 被拒绝 |
| 295 | 安全锁验证失败 |
| 299 | IAM 权限校验未通过 |

## 快速开始

### 准备工作

1. 获取 [API 访问地址](api/summary/gateway)
2. 从 [UAPI 控制台](https://console.ucloud.cn/uapi/apikey) 获取 API 密钥，包括 `PublicKey` 和 `PrivateKey`
3. 如果待操作资源属于某个地域下，[获取地域和可用区列表](api/summary/regionlist)
4. 如果账号属于子账号，或需要操作某个特定项目，[获取项目 ID](api/summary/regionlist)

### 发起请求

您可以通过多种方式向 API 访问地址发起请求，包括 [cURL](https://curl.haxx.se/)、[Postman](https://www.postman.com/) 等客户端，以及 [UAPI 浏览器](https://console.ucloud.cn/uapi/ucloudapi)、[CLI](https://docs.ucloud.cn/cli/)、SDK 等。
建议使用 [UAPI 浏览器](https://console.ucloud.cn/uapi/ucloudapi)，构造并发起请求后，可自动生成 SDK 样例。

UCloud API 支持 `GET` / `POST` 两种方法，支持 `application/json` 和 `application/x-www-form-urlencoded` 两种请求方式。

本文以 cURL POST JSON 为例，描述如何构造并发起一个 HTTP 请求。

**数据假设**

本例中假设

```
PublicKey  = 'ucloudsomeone@example.com1296235120854146120'
PrivateKey = '46f09bb9fab4f12dfc160dae12273d5332b5debe'
```

假设用户请求参数如下:

```json
{
    "Action"     :  "DescribeUHostInstance",
    "Region"     :  "cn-bj2",
    "Limit"      :  10
}
```

**计算签名**

可参考 [签名算法](api/summary/signature) 文档，计算出的 `Signature` 为 **cba5cf5ec4d4233d206b1b54951e3787350a642f** 。

**构造请求**

将 `PublicKey` 和 `Signature` 填入请求参数中，构造出的请求最终为：

```bash
curl -X POST \
  https://api.ucloud.cn \
  -H 'Content-Type: application/json' \
  -d '{
      "Action"     :  "DescribeUHostInstance",
      "Limit"      :  10,
      "PublicKey"  :  "ucloudsomeone@example.com1296235120854146120",
      "Region"     :  "cn-bj2",
      "Signature"  :  "cba5cf5ec4d4233d206b1b54951e3787350a642f"
  }'
```
