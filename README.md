# HeyWords 官网

这是 HeyWords 应用的官方网站，包含产品介绍、隐私政策和服务条款。

## 📁 文件结构

```
website/
├── index.html      # 官网首页
├── privacy.html    # 隐私政策
├── terms.html      # 服务条款
├── images/         # 图片资源
│   ├── logo@800.png       # Logo 图标
│   └── logo-name@800.png  # Logo 文字
└── README.md       # 说明文档
```

## 🚀 部署方式

### 方式一：Vercel（推荐）

1. 在 GitHub 上创建仓库并推送这个 website 目录
2. 访问 [vercel.com](https://vercel.com)
3. 导入 GitHub 仓库
4. Vercel 会自动部署
5. 在 Vercel 设置中绑定自定义域名 `heywords.app`

**优点**：免费、自动部署、全球 CDN

### 方式二：Cloudflare Pages

1. 登录 [Cloudflare](https://dash.cloudflare.com)
2. 进入 Pages 服务
3. 连接 Git 仓库或直接上传文件
4. 配置自定义域名

**优点**：免费、速度快、Cloudflare CDN

### 方式三：腾讯云 COS + CDN

1. 创建 COS 存储桶
2. 上传所有 HTML 文件
3. 配置静态网站托管
4. 绑定 CDN 和自定义域名

**优点**：国内访问极快，适合中国用户

## 🔗 URL 规划

部署后，访问地址将是：

```
https://heywords.app/           # 官网首页
https://heywords.app/privacy    # 隐私政策
https://heywords.app/terms      # 服务条款
```

## ✏️ 自定义修改

### 修改 App Store 链接

在 `index.html` 中找到：
```html
<a href="https://apps.apple.com/app/id6753859247" class="app-store-btn">
```

### 修改联系邮箱

在 `privacy.html` 和 `terms.html` 中找到：
```html
<strong>邮箱：</strong> support@heywords.app
```

### 修改颜色主题

在各 HTML 文件的 `<style>` 标签中修改：
```css
:root {
    --primary-gradient: linear-gradient(135deg, #C48709 0%, #1C940E 100%);
}
```

## 📱 iOS 应用配置

部署完成后，需要在 iOS 应用中更新链接：

1. 打开 `SettingsView.swift`
2. 更新底部的链接：

```swift
private var footerSection: some View {
    // ...
    HStack(spacing: 5) {
        Link("服务条款", destination: URL(string: "https://heywords.app/terms")!)
        Text("·")
        Link("隐私政策", destination: URL(string: "https://heywords.app/privacy")!)
    }
}
```

## 🎨 设计说明

- **首页**：现代简洁风格，突出产品核心价值
- **隐私政策**：移动端友好，清晰易读
- **服务条款**：专业规范，符合法律要求
- **响应式设计**：自适配手机、平板、电脑

## 📝 注意事项

1. **App Store 审核**：隐私政策和服务条款需要在 App Store Connect 的"应用隐私"部分填写链接
2. **域名备案**：如果使用国内服务器（如腾讯云），建议进行 ICP 备案
3. **HTTPS**：所有现代部署平台都会自动提供 SSL 证书

## 🔄 更新内容

如需更新隐私政策或服务条款：
1. 修改对应的 HTML 文件
2. 更新"最后更新日期"
3. 推送到 Git 仓库（Vercel/Cloudflare 会自动重新部署）

---

**设计与开发**: HeyWords Team  
**最后更新**: 2025年1月

