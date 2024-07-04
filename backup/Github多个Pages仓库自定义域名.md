### 设置自定义域名

#### 1. 登录到你的 Cloudflare 账号
1. 选择你的域名（例如 `yourdomain.com`）。
2. 进入 DNS 设置，添加一条新的 CNAME 记录：
   - 名称 (Name): `@`
   - 目标 (Target): `example.com`
   - TTL: 自动
   - Proxy status: 可选（可以选择通过 Cloudflare 代理或仅 DNS）。

### 设置页面规则

#### 2. 在 Cloudflare 仪表板中
1. 选择“页面规则”（Page Rules）。
2. 添加一个新的页面规则，设置以下参数：
   - URL 匹配: `yourdomain.com/*`
   - 添加一个转发 URL（Forwarding URL）规则：
     - 选择“301 重定向”（永久重定向）。
     - 设置目标 URL 为 `https://example.com/example/$1`。
     - 点击“保存并部署”页面规则。

完成这些步骤后，当你访问 `yourdomain.com` 时，Cloudflare 将自动重定向到 `https://example.com/example`。

### 如果你希望自定义域名直接展示博客内容而不是重定向，可以参考以下方法：

#### 1. 设置自定义域名到 GitHub Pages
1. 进入你的 GitHub Pages 项目仓库（`example.com/example`）。
2. 在仓库的根目录创建一个名为 `CNAME` 的文件，并在文件中写入你想要使用的自定义域名，例如 `yourdomain.com`。

### 设置 Cloudflare

#### 2. 登录到你的 Cloudflare 账号
1. 在 Cloudflare 仪表板中选择你的网站（例如 `yourdomain.com`）。
2. 进入 DNS 设置，添加一条新的 CNAME 记录：
   - 名称 (Name): `@`
   - 目标 (Target): `example.com`
   - TTL: 自动（或你想要的时间）
   - Proxy status: 可选（可以选择通过 Cloudflare 代理或仅 DNS）

完成这些步骤后，你的博客应该可以通过 `yourdomain.com` 访问了，直接展示博客内容而不是重定向。