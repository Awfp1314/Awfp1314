# GitHub Profile 配置指南

这个仓库是你的 GitHub 个人主页 README，包含自动更新功能。

## 功能特性

### 1. WakaTime 编码统计（自动更新）

显示你的编码时间、使用的语言、编辑器等统计信息。

**配置步骤：**

1. 注册 WakaTime 账号：https://wakatime.com/
2. 在 VS Code 中安装 WakaTime 插件
3. 获取 WakaTime API Key：
   - 登录 WakaTime
   - 进入 Settings → API Key
   - 复制你的 API Key

4. 配置 GitHub Secrets：
   - 进入仓库 Settings → Secrets and variables → Actions
   - 添加 `WAKATIME_API_KEY`：粘贴你的 WakaTime API Key
   - 添加 `GH_TOKEN`：
     - 进入 GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
     - 生成新 token，勾选 `repo` 和 `workflow` 权限
     - 复制 token 并添加到 Secrets

5. 手动触发首次更新：
   - 进入仓库 Actions 标签
   - 选择 "Waka Readme" workflow
   - 点击 "Run workflow"

**更新频率：** 每天自动更新一次（北京时间早上 8:00）

### 2. 最近博客列表（自动更新）

自动从你的博客仓库 (awfp1314.github.io) 抓取最新的 4 篇文章。

**工作原理：**

- 每天自动运行
- 读取博客仓库的 MDX 文件
- 提取标题、描述和发布日期
- 按日期排序，更新 README

**手动触发：**

- 进入 Actions 标签
- 选择 "Update Recent Blog Posts" workflow
- 点击 "Run workflow"

**更新频率：** 每天自动更新一次，或每次推送到 main 分支时更新

### 3. GitHub 统计卡片（实时）

显示你的 GitHub 统计信息和最常用语言，无需配置，实时生成。

## 维护说明

### 更新个人信息

直接编辑 `README.md` 文件中的以下部分：

- 关于我
- 技术栈
- 项目展示
- 联系方式

### 添加新项目

在 "项目展示" 部分添加新的项目卡片，格式参考现有项目。

### 博客列表

博客列表会自动更新，无需手动维护。如果需要立即更新，可以手动触发 workflow。

## 故障排查

### WakaTime 不显示数据

1. 检查 Secrets 是否正确配置
2. 确认 WakaTime 插件已安装并登录
3. 等待至少一天让 WakaTime 收集数据
4. 手动触发 workflow 查看错误日志

### 博客列表不更新

1. 检查博客仓库是否有新文章
2. 确认文章的 frontmatter 格式正确
3. 手动触发 workflow 查看错误日志

## 相关链接

- WakaTime 官网：https://wakatime.com/
- GitHub Stats 卡片：https://github.com/anuraghazra/github-readme-stats
- 博客仓库：https://github.com/Awfp1314/awfp1314.github.io
