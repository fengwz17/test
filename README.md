在 GitHub 上，Liquid 模板引擎主要通过 Jekyll 静态网站生成器使用，Jekyll 是 GitHub Pages 的默认支持工具。要在 GitHub 上使用 Liquid 模板，你可以通过 Jekyll 来创建和管理静态网站。下面是如何在 GitHub 上使用 Liquid 模板的详细步骤。

### 步骤 1：创建一个 GitHub 仓库

1. 登录你的 GitHub 账号，创建一个新的仓库。如果你希望它是一个 GitHub Pages 站点，建议将仓库命名为 `<username>.github.io`，其中 `<username>` 是你的 GitHub 用户名。该仓库将自动被配置为 GitHub Pages 站点。
   
2. 在新仓库中，你可以推送带有 Jekyll 文件的网站内容。

### 步骤 2：启用 GitHub Pages 和 Jekyll
1. 创建并推送以下基本文件结构到你的仓库：

    - `_config.yml` (Jekyll 配置文件)
    - `_layouts` 文件夹 (用于存储页面布局)
    - `_includes` 文件夹 (可选，用于存储可重用的页面片段)
    - `index.md` (主页文件)

2. 在 `Settings` -> `Pages` 中，设置 GitHub Pages 的分支（一般使用 `main` 或 `gh-pages`）。

### 步骤 3：创建 `_config.yml`
`_config.yml` 是 Jekyll 的配置文件，用于设置网站标题、描述和其他配置信息。你可以在这里定义自定义变量来使用 Liquid 模板语法。

```yaml
title: My GitHub Pages Site
description: This is my static website using Jekyll and Liquid.
```

### 步骤 4：使用 Liquid 模板
Liquid 模板可以帮助你在页面中动态渲染变量和结构。你可以在页面、布局文件中使用 Liquid 语法。

#### 1. 创建布局文件
在仓库的根目录下，创建 `_layouts/default.html` 文件，作为页面的默认布局。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title }}</title>
</head>
<body>
  <header>
    <h1>{{ site.title }}</h1>
    <p>{{ site.description }}</p>
  </header>
  
  <main>
    {{ content }}
  </main>

  <footer>
    <p>Powered by Jekyll and GitHub Pages.</p>
  </footer>
</body>
</html>
```

#### 2. 创建主页文件 `index.md`
在根目录下，创建 `index.md` 文件，用来定义主页的内容，并将其应用于刚才定义的布局文件。

```markdown
---
layout: default
title: Home
---

## Welcome to My GitHub Pages

This site is generated using Jekyll and powered by Liquid templates.
```

#### 3. 使用 Liquid 变量
在 `_config.yml` 中你可以定义自定义的变量，然后通过 Liquid 模板语法在布局文件或页面中引用：

```yaml
title: My GitHub Pages Site
description: This is my static website using Jekyll and Liquid.
my_macro: "jia xiang liu [member]"
```

在页面中使用：

```markdown
{{ site.my_macro }}
```

这个 `{{ site.my_macro }}` 会被自动替换为 `_config.yml` 文件中定义的内容，即 `jia xiang liu [member]`。

### 步骤 5：提交并推送到 GitHub
1. 将所有更改提交到本地 Git 仓库并推送到 GitHub 仓库。
2. GitHub Pages 会自动构建和部署 Jekyll 网站。

### 步骤 6：访问 GitHub Pages 站点
一旦 GitHub Pages 部署完成，你可以通过 `https://<username>.github.io` 来访问生成的静态网站，并看到使用了 Liquid 模板的内容。

---

通过这个过程，你可以在 GitHub Pages 上使用 Liquid 模板来创建动态的静态网站，并通过 Jekyll 进行管理。
