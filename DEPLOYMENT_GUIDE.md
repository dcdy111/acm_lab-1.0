# GitHub Pages 部署指南

## 🚀 部署步骤

### 1. 准备工作

您的项目已经完成了以下优化：
- ✅ 修复了所有绝对路径问题
- ✅ 创建了GitHub Actions工作流
- ✅ 添加了.gitignore文件
- ✅ 验证了所有资源文件完整性

### 2. 启用GitHub Pages

#### 方法一：通过GitHub仓库设置启用

1. 进入您的GitHub仓库：`https://github.com/dcdy111/acm_lab-1.0`
2. 点击 **Settings** 标签页
3. 在左侧菜单中找到 **Pages**
4. 在 **Source** 部分选择：
   - **Deploy from a branch** → 选择 `main` 或 `master` 分支
   - 或者选择 **GitHub Actions**（推荐）

#### 方法二：使用GitHub Actions（推荐）

1. 确保您的仓库中有 `.github/workflows/deploy.yml` 文件
2. 在 **Settings** → **Pages** 中：
   - Source 选择 **GitHub Actions**
   - 保存设置

### 3. 推送代码到GitHub

```bash
# 初始化Git仓库（如果还没有）
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Initial commit: ACM Lab static site ready for deployment"

# 添加远程仓库
git remote add origin https://github.com/dcdy111/acm_lab-1.0.git

# 推送到GitHub
git push -u origin main
```

### 4. 触发部署

推送代码后，GitHub Actions会自动开始部署。您可以在：
- **Actions** 标签页查看部署进度
- 等待部署完成（通常需要2-5分钟）

### 5. 访问您的网站

部署成功后，您的网站将在以下地址可用：
- `https://dcdy111.github.io/acm_lab-1.0/`

## 🔧 故障排除

### 问题1：Pages未启用
**错误**：`Get Pages site failed`
**解决方案**：
1. 确保在仓库设置中启用了Pages
2. 选择正确的源（分支或GitHub Actions）

### 问题2：部署失败
**解决方案**：
1. 检查Actions日志中的具体错误信息
2. 确保所有文件都已正确提交
3. 检查是否有语法错误

### 问题3：资源文件404
**解决方案**：
1. 确保所有图片和资源文件都在正确位置
2. 检查路径是否为相对路径

## 📁 项目结构确认

您的项目包含以下关键文件：
```
static_site/
├── .github/workflows/deploy.yml    # GitHub Actions配置
├── .gitignore                      # Git忽略文件
├── index.html                      # 主页
├── site_index.html                 # 网站导航
├── team.html                       # 团队页面
├── algorithm.html                  # 算法页面
├── paper.html                      # 论文页面
├── innovation.html                 # 创新页面
├── dynamic.html                    # 动态页面
├── introduction.html               # 介绍页面
├── matrix.html                     # Matrix页面
├── data/                          # 数据文件
├── css/                           # 样式文件
├── js/                            # JavaScript文件
├── images/                        # 图片资源
└── uploads/                       # 上传文件
```

## 🌐 访问地址

部署成功后，您可以通过以下方式访问：
- 主页：`https://dcdy111.github.io/acm_lab-1.0/`
- 团队页面：`https://dcdy111.github.io/acm_lab-1.0/team.html`
- 算法页面：`https://dcdy111.github.io/acm_lab-1.0/algorithm.html`
- 其他页面类似...

## 📝 更新网站

如需更新网站内容：
1. 修改本地文件
2. 提交更改：`git add . && git commit -m "Update content"`
3. 推送到GitHub：`git push origin main`
4. GitHub Actions会自动重新部署

## ⚠️ 注意事项

1. **首次部署**可能需要等待几分钟才能生效
2. **自定义域名**：如需使用自定义域名，请编辑 `CNAME` 文件
3. **HTTPS**：GitHub Pages自动提供HTTPS支持
4. **缓存**：浏览器可能会缓存旧版本，请强制刷新（Ctrl+F5）

## 🆘 需要帮助？

如果遇到问题，请检查：
1. GitHub仓库的Pages设置
2. Actions标签页的部署日志
3. 确保所有文件都已正确上传

祝您部署成功！🎉
