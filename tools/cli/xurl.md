# xurl

https://github.com/xdevplatform/xurl

X API 的命令行客户端，类似 curl，但内置 OAuth 认证，请求时自动带上 token。

## Installation

```bash
brew install --cask xdevplatform/tap/xurl
xurl --version
```

## Authentication

凭证存在 `~/.xurl`。

```bash
# 注册 app，CLIENT_ID / CLIENT_SECRET 来自 X Developer Portal
xurl auth apps add lalalalisa \
  --client-id <CLIENT_ID> \
  --client-secret <CLIENT_SECRET> \
  --redirect-uri http://localhost:8080/callback

# 走 OAuth 2.0 授权流程
xurl auth oauth2 --app lalalalisa

# 查看认证状态、设置默认 app
xurl auth status
xurl auth default lalalalisa
```

`--redirect-uri` 要和 Developer Portal 里填的 Callback URI 完全一致。

## Usage

```bash
xurl user xdevelopers
xurl search "OpenAI"
xurl post "Hello from xurl"
```
