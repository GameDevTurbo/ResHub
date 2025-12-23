# ResHub - 图床仓库

中文 | [English](./README.md)

## 概述

ResHub 是一个个人图床仓库，旨在使用 GitHub 作为后端存储来存储和提供博客、文档和其他用途的图片。

## 如何在移动端使用

### 方案一：PicGo 移动版替代 - PicList（推荐）

由于 PicGo 桌面版没有官方移动应用，您可以使用 **PicList**，它同时支持桌面和移动平台。

#### Android 用户：
1. 从 [GitHub Releases](https://github.com/Kuingsmile/PicList) 下载 PicList
2. 在您的 Android 设备上安装 APK
3. 配置 GitHub 作为上传目标：
   - **Token**：您的 GitHub 个人访问令牌（需要 `repo` 权限）
   - **仓库名**：`GameDevTurbo/ResHub`
   - **分支**：`main`
   - **存储路径**：选择您的文件夹（例如 `img/`、`TyproaPic/` 等）
   - **自定义域名**：`https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/`

#### iOS 用户：
由于 iOS 的限制，建议使用下面的方案二或方案三。

### 方案二：GitHub 移动应用

1. 在移动设备上安装官方 GitHub 应用
2. 导航到 ResHub 仓库
3. 浏览到您想要上传图片的文件夹
4. 点击 "+" 按钮并选择 "Upload files"
5. 从相册或相机中选择图片
6. 添加提交信息并直接提交到 main 分支

**优点**：官方 GitHub 应用，安全可靠  
**缺点**：无图片压缩，无批量操作，不够便捷

### 方案三：Termux + Git（仅 Android）

适合 Android 高级用户：

1. 从 F-Droid 安装 [Termux](https://f-droid.org/packages/com.termux/)
2. 设置 Git：
   ```bash
   pkg install git
   git config --global user.name "您的名字"
   git config --global user.email "您的邮箱"
   ```
3. 克隆仓库：
   ```bash
   cd ~/storage/shared
   git clone https://github.com/GameDevTurbo/ResHub.git
   cd ResHub
   ```
4. 上传图片：
   ```bash
   cp ~/storage/dcim/Camera/photo.jpg ./img/
   git add .
   git commit -m "上传图片"
   git push
   ```

**优点**：完整的 Git 功能，可脚本化  
**缺点**：需要技术知识，基于终端

### 方案四：第三方图床应用

一些移动应用支持上传到 GitHub：

- **uPic**（iOS）：支持 GitHub 作为后端
- **基于 PicGo-Core 的应用**：搜索社区开发的移动版本

## 设置 GitHub 个人访问令牌

要使用上述任何方法（GitHub 移动应用除外），您需要一个个人访问令牌：

1. 前往 [GitHub 设置 > 开发者设置 > 个人访问令牌](https://github.com/settings/tokens)
2. 点击 "Generate new token (classic)"
3. 给它一个名称（例如 "ResHub 移动上传"）
4. 选择 `repo` 权限（私有仓库的完全控制）
5. 点击 "Generate token"
6. **重要**：立即复制令牌 - 您将无法再次看到它！

## 仓库结构

```
ResHub/
├── TyproaPic/     # 通过 Typora 上传的图片
├── img/           # 通用图片
├── picG/          # PicGo 上传
└── picGoGoGo/     # 其他图片
```

## 获取图片 URL

上传后，您可以使用以下方式访问图片：

### 原始 URL（直接访问）：
```
https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/[文件夹]/[文件名]
```

### HTML 图片标签：
```html
<img src="https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/img/example.png" alt="描述">
```

### Markdown：
```markdown
![描述](https://raw.githubusercontent.com/GameDevTurbo/ResHub/main/img/example.png)
```

## 移动端使用技巧

1. **图片压缩**：上传前压缩图片以节省带宽和存储空间
2. **有序的文件夹**：使用一致的文件夹名称以便更好地组织
3. **提交信息**：使用描述性的提交信息以便更容易跟踪
4. **CDN 替代方案**：考虑使用 jsDelivr 加快图片加载：
   ```
   https://cdn.jsdelivr.net/gh/GameDevTurbo/ResHub@main/img/example.png
   ```

## 常见问题

### 上传失败
- 检查您的 GitHub 令牌权限
- 验证仓库名称是否正确
- 确保您对仓库有写入权限

### 图片无法加载
- GitHub 原始 URL 在某些地区可能较慢
- 尝试使用 jsDelivr CDN 作为替代
- 检查图片路径是否正确

### 令牌过期
- GitHub 令牌除非您设置了过期日期，否则不会过期
- 如果过期，请按照上述步骤生成新令牌

## 许可证

此仓库供个人使用。所有图片仍归其各自所有者所有。
