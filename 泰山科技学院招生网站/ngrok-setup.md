# ngrok 认证设置指南

## 错误信息：ERR_NGROK_4018

这个错误表示 ngrok 需要认证才能使用。你需要：

## 步骤 1：注册 ngrok 账号

1. 访问 https://dashboard.ngrok.com/signup
2. 使用邮箱注册账号
3. 验证邮箱

## 步骤 2：获取认证令牌

1. 登录 https://dashboard.ngrok.com/get-started/setup
2. 在 "Your Authtoken" 部分找到你的认证令牌
3. 复制这个令牌

## 步骤 3：配置认证

### 方法 A：命令行配置

在命令提示符中运行：

```bash
ngrok.exe authtoken 你的认证令牌
```

### 方法 B：手动创建配置文件

1. 在 Windows 上，创建以下文件：
   - `C:\Users\你的用户名\.ngrok2\ngrok.yml`

2. 文件内容：
   ```yaml
auth_token: 你的认证令牌
```

## 步骤 4：重新运行 ngrok

```bash
ngrok.exe http 8000
```

## 步骤 5：获取公网链接

运行后，你会看到类似这样的输出：

```
Session Status                online
Account                       你的账号 (Plan: Free)
Version                       2.3.40
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://abc123.ngrok.io -> http://localhost:8000
Forwarding                    https://abc123.ngrok.io -> http://localhost:8000

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```

### 分享链接

复制 `Forwarding` 部分的链接，例如：
- `http://abc123.ngrok.io` 或 `https://abc123.ngrok.io`

这个链接就是你的公网访问地址，可以分享到微信！

## 注意事项

- 免费版 ngrok 链接会在 8 小时后过期
- 每次重启 ngrok 都会生成新的链接
- 网站需要保持服务器运行（不要关闭命令窗口）

## 测试链接

1. 在浏览器中打开生成的 ngrok 链接
2. 测试所有跳转功能
3. 确认可以正常访问后，分享到微信

现在你就可以通过微信分享你的网站了！