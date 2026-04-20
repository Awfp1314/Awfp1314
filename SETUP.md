# GitHub Profile 动态统计配置指南

## 📋 前置要求

1. GitHub 账号
2. WakaTime 账号（免费）

## 🚀 配置步骤

### 1. 注册 WakaTime

1. 访问 [WakaTime](https://wakatime.com/)
2. 使用 GitHub 账号登录
3. 进入 [Settings → API Key](https://wakatime.com/settings/api-key)
4. 复制你的 API Key

### 2. 安装 WakaTime 插件

根据你使用的编辑器安装对应插件：

- **VS Code**: 在扩展商店搜索 "WakaTime"
- **PyCharm**: Settings → Plugins → 搜索 "WakaTime"
- **其他编辑器**: 查看 [WakaTime 插件列表](https://wakatime.com/plugins)

安装后输入你的 API Key。

### 3. 配置 GitHub Secrets

1. 进入你的 GitHub Profile 仓库（`Awfp1314/Awfp1314`）
2. 点击 `Settings` → `Secrets and variables` → `Actions`
3. 添加以下两个 Secret：

#### Secret 1: WAKATIME_API_KEY

- Name: `WAKATIME_API_KEY`
- Value: 你的 WakaTime API Key

#### Secret 2: GH_TOKEN

- Name: `GH_TOKEN`
- Value: GitHub Personal Access Token

**创建 GitHub Token**：

1. 访问 [GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)](https://github.com/settings/tokens)
2. 点击 `Generate new token (classic)`
3. 设置：
   - Note: `Waka Readme Stats`
   - Expiration: `No expiration`（或选择一个时间）
   - 勾选权限：
     - ✅ `repo` (所有子选项)
     - ✅ `user` (所有子选项)
4. 点击 `Generate token`
5. 复制生成的 token（只显示一次！）

### 4. 推送代码

```bash
cd GithubProject/Awfp1314
git add .
git commit -m "feat: 添加 WakaTime 动态统计"
git push origin main
```

### 5. 手动触发第一次运行

1. 进入仓库的 `Actions` 标签页
2. 点击左侧的 `Waka Readme`
3. 点击右侧的 `Run workflow` → `Run workflow`
4. 等待几分钟，查看 README 是否更新

## 📊 统计内容

配置完成后，README 会自动显示：

- 📝 **代码行数统计** - 从 "Hello World" 开始写了多少行代码
- 🏆 **GitHub 数据** - 存储使用、贡献次数、仓库数量
- 🌙 **工作时间分布** - 早晨/白天/晚上/深夜的代码量
- 📅 **每周活跃度** - 周一到周日的提交分布
- 💻 **编程语言** - 使用最多的编程语言
- 🖥️ **操作系统** - 开发环境统计
- 📂 **项目统计** - 在哪些项目上花费时间最多
- ⏰ **时区信息** - 你的工作时区

## 🔄 更新频率

- **自动更新**: 每天 UTC 0:00（北京时间 8:00）
- **手动触发**: 在 Actions 页面手动运行

## ⚠️ 注意事项

1. **WakaTime 需要时间收集数据**
   - 安装插件后需要编码一段时间才有数据
   - 建议至少编码 1-2 天后再查看统计

2. **GitHub Token 权限**
   - 确保 token 有足够的权限
   - Token 过期后需要重新生成并更新 Secret

3. **隐私设置**
   - WakaTime 默认统计所有项目
   - 可以在 WakaTime 设置中排除特定项目

## 🎨 自定义配置

如果想调整显示内容，编辑 `.github/workflows/waka-readme.yml`：

```yaml
SHOW_LINES_OF_CODE: "True" # 显示代码行数
SHOW_COMMIT: "True" # 显示提交统计
SHOW_DAYS_OF_WEEK: "True" # 显示每周活跃度
SHOW_LANGUAGE: "True" # 显示编程语言
SHOW_OS: "True" # 显示操作系统
SHOW_PROJECTS: "True" # 显示项目统计
SHOW_TIMEZONE: "True" # 显示时区
SHOW_EDITORS: "True" # 显示编辑器
```

## 🔗 相关链接

- [WakaTime 官网](https://wakatime.com/)
- [waka-readme-stats GitHub](https://github.com/anmol098/waka-readme-stats)
- [GitHub Actions 文档](https://docs.github.com/en/actions)

## ❓ 常见问题

### Q: 为什么统计数据不显示？

A:

1. 检查 WakaTime 插件是否正常工作
2. 确认 API Key 配置正确
3. 等待至少 1-2 天让 WakaTime 收集数据

### Q: 如何排除某些项目？

A: 在 WakaTime 设置中添加项目到排除列表

### Q: 统计数据多久更新一次？

A: 默认每天更新一次，也可以手动触发

---

配置完成后，你的 GitHub Profile 就会像参考项目一样酷炫了！🎉
