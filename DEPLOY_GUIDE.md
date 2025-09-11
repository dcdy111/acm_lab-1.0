# GitHub Pages 部署指南

## 🚀 快速部署

### 方法一：GitHub Web界面上传

1. 在GitHub上创建新仓库（如：`acm-lab-website`）
2. 将 `static_site` 目录下的所有文件上传到仓库根目录
3. 进入仓库设置（Settings）
4. 滚动到 "Pages" 部分
5. 在 "Source" 下选择 "Deploy from a branch"
6. 选择 "main" 分支和 "/ (root)" 文件夹
7. 点击 "Save"
8. 等待几分钟，您的网站将在 `https://username.github.io/repository-name` 上线

### 方法二：Git命令行部署

```bash
# 进入静态网站目录
cd static_site

# 初始化Git仓库
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Initial commit: ACM Lab static website"

# 添加远程仓库（替换为您的仓库URL）
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git

# 推送到主分支
git push -u origin main
```

## ⚠️ 重要注意事项

1. **确保所有文件都在仓库根目录**：不要将静态文件放在子文件夹中
2. **检查文件大小**：GitHub有100MB单文件限制，确保图片等资源文件不超过此限制
3. **路径问题**：本转换器已自动修复所有路径，确保相对路径正确
4. **缓存问题**：GitHub Pages可能有缓存延迟，更新后需要等待几分钟

## 🔧 自定义域名（可选）

如果您有自定义域名：

1. 将 `CNAME.template` 重命名为 `CNAME`
2. 编辑CNAME文件，只包含您的域名（如：`www.example.com`）
3. 在您的域名注册商处设置DNS记录指向GitHub Pages

## 📊 验证部署

部署成功后，访问您的网站并检查：

- ✅ 页面样式正常显示
- ✅ 图片正确加载
- ✅ 页面导航正常工作
- ✅ 图标正常显示
- ✅ 响应式布局工作正常

## 🆘 常见问题

### 样式丢失
- 确保CSS文件路径正确
- 检查浏览器开发者工具的Network选项卡

### 图片无法显示  
- 确保图片文件已正确上传
- 检查图片路径大小写是否正确

### 图标不显示
- 检查网络连接，图标使用CDN加载
- 确保FontAwesome CDN链接有效

生成时间: 2025-09-11 14:39:46
