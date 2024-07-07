我们一般建立第一个GitHub Pages仓库的时候，仓库名如果跟自己的用户名一样，GitHub会给你分配一个相同的域名。例如你的用户名是`example`，你的仓库名也是`example`
`Gmeek-html<img src="https://github.com/ischriswong/photo/blob/main/Github多个Pages仓库自定义域名/1.png?raw=true">`

那GitHub会给你分配一个`example.github.io`的域名
`Gmeek-html<img src="https://github.com/ischriswong/photo/blob/fa179cad3bc3f9cb88d686b8e2a4f7bf64b3f41b/Github多个Pages仓库自定义域名/2.png?raw=true">`

这时候你要自定义域名的话，直接去Cloudflare上正常解析就行了。

但是后续你再创建仓库的话，比如创建一个名为`music`的仓库，它给你分配的域名就成了`example.github.io/music`。那么这样的域名怎么自定义呢？

## 1. 设置自定义域名到 GitHub Pages

1. 进入你的 GitHub Pages 项目仓库（`example.github.io/music`）。
2. 点击 **Settings**，再点击 **Pages**，然后在 **Custom domain** 输入你想要使用的自定义域名，例如 `yourdomain.com`，点击 **Save**。这时候在仓库的根目录会自动创建一个名为 `CNAME` 的文件。
`Gmeek-html<img src="https://github.com/ischriswong/photo/blob/main/Github多个Pages仓库自定义域名/3.png?raw=true">`

## 2. 设置 Cloudflare

1. 登录到你的 Cloudflare 账号。
2. 在 Cloudflare 仪表板中选择你的网站（例如 `yourdomain.com`）。
3. 进入 **DNS 设置**，添加一条新的 CNAME 记录：
   - 名称 (Name): @
   - 目标 (Target): `example.github.io`
   - TTL: 自动（或你想要的时间）
   - Proxy status: 可选（可以选择通过 Cloudflare 代理或仅 DNS）
`Gmeek-html<img src="https://github.com/ischriswong/photo/blob/main/Github多个Pages仓库自定义域名/4.png?raw=true">`

完成这些步骤后，你的博客应该可以通过 `yourdomain.com` 访问了。
