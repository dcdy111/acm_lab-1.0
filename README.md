# ACM算法研究实验室 - 静态网站

## 📋 项目说明

这是从Flask动态网站转换而来的静态网站版本，包含了实验室的所有核心展示内容。

## 🚀 特性

- ✅ **完整数据展示**: 包含团队成员、算法研究、学术论文、科技创新等所有数据
- ✅ **静态化部署**: 可直接部署到GitHub Pages、Netlify等静态托管服务
- ✅ **轻量化设计**: 移除了动态功能，保留核心展示功能
- ✅ **响应式布局**: 支持PC和移动端访问
- ✅ **SEO友好**: 静态HTML有利于搜索引擎收录

## 📁 文件结构

```
static_site/
├── index.html              # 实验室首页
├── site_index.html         # 网站导航首页
├── team.html               # 团队成员页面
├── algorithm.html          # 算法研究页面
├── paper.html              # 学术论文页面
├── innovation.html         # 科技创新页面
├── dynamic.html            # 实验室动态页面
├── introduction.html       # 实验室介绍页面
├── matrix.html             # Matrix展示页面
├── notification/           # 通知详情页面目录
├── data/                   # 静态数据文件
├── css/                    # 样式文件
├── js/                     # JavaScript文件
├── images/                 # 图片资源
└── uploads/                # 上传文件
```

## 🌐 部署方式

### GitHub Pages 部署

1. 将整个 `static_site` 目录内容上传到GitHub仓库
2. 在仓库设置中启用GitHub Pages
3. 选择主分支作为发布源
4. 访问 `https://username.github.io/repository-name`

### Netlify 部署

1. 将 `static_site` 目录压缩为zip文件
2. 登录Netlify并拖拽zip文件到部署区域
3. 等待部署完成并获取访问链接

### 本地预览

使用Python内置服务器：
```bash
cd static_site
python -m http.server 8000
```
然后访问 `http://localhost:8000`

## 📊 数据说明

- 所有数据已从SQLite数据库导出为JSON格式
- 数据文件位于 `data/` 目录下
- 页面通过JavaScript异步加载JSON数据
- 数据结构与原API接口保持一致

## ⚠️ 注意事项

- 这是静态版本，不支持数据编辑和管理功能
- 不支持用户登录和实时同步
- 如需更新数据，请重新运行转换器
- 建议定期从源网站更新静态版本

## 🔧 生成信息

- 生成时间: 2025-09-11 12:26:11
- 转换器版本: 1.0.0
- 源项目: ACM算法研究实验室管理系统

## 📞 联系方式

如有问题或建议，请联系实验室管理员。
