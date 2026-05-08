# 呱呱个人工具页

一个纯静态个人工具集合页面，适合部署到 GitHub Pages。

## 页面入口

- `index.html`：个人引导页
- `Reading/yuedu.html`：阅读书源去重工具
- `DS/mfgy.html`：魔法工艺九宫格熄灯小游戏解密工具
- `404.html`：404 提示页

## 功能说明

### 阅读书源去重

支持两种导入方式：

- 选择本地 JSON 文件，可一次选择多个文件
- 输入网络 JSON 地址，每行一个 URL

处理逻辑：

- 自动解析源仓库 API 返回的 `msg`、`downloadUrl` 或 `url` 直链
- 对 `yck2026.top` 这类无 CORS 响应头的地址，会尝试多个公共 CORS 代理
- 成功解析的 URL、加载失败的 URL、无效书源会分开展示
- 按 `bookSourceUrl` 的域名去重
- 跳过 `bookSourceUrl` 不是合法 URL 的无效书源
- 生成可下载的去重后 JSON 文件

### 魔法工艺解密

九宫格熄灯小游戏辅助工具，支持：

- 随机模式练习
- 游戏内当前设置模式
- 一键生成解密步骤
- 特殊模式生成

## 部署

本项目不需要构建工具，直接部署静态文件即可。

GitHub Pages 推荐设置：

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/ (root)`

部署后访问：

```text
https://<你的用户名>.github.io/gua/
```

## 说明

项目已移除生产环境不适合使用的 Tailwind CDN 和外部图标依赖，页面样式均为本地 CSS。
