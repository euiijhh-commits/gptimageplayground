# 大王的生图工作台 · GitHub Pages 静态包

本目录是纯静态构建产物（83 个文件的原始镜像 + `.nojekyll` + 本说明），无需 npm install、无需构建、无需 GitHub Actions。

## 部署步骤

1. 在 GitHub 新建一个 **Public** 仓库，建议命名 `gptimageplayground`。
2. 把本目录内**所有文件**（含 `.nojekyll`）上传到仓库 `main` 分支的**根目录**。
   - GitHub 网页支持一次拖拽多个文件；也可用 git 命令行 push。
   - 若网页上传忽略了 `.nojekyll`，请在仓库网页上新建同名空文件，避免 Jekyll 处理静态资源。
3. 打开仓库 **Settings → Pages**，将 **Build and deployment → Source** 设为 **Deploy from a branch**，分支选 `main`、目录选 `/ (root)`，保存。
4. 等待 1–2 分钟，访问：
   `https://<你的用户名>.github.io/gptimageplayground/`
   （若仓库命名为 `<你的用户名>.github.io`，则地址为 `https://<你的用户名>.github.io/`）

## 使用前提

页面为纯前端，本身不含算力。打开后进入「设置 → API 配置」填入你自己的图像 API Base URL 与 Key；Key 只保存在浏览器本地。

资源全部使用相对路径（`./assets/...`），因此在项目子路径下也可正常加载；`sw.js` 的 Service Worker scope 会自动适配仓库子路径。

## 注意

- GitHub Pages 为 HTTPS 站点，浏览器会拦截对本地/内网 HTTP API 的请求；若需调用 HTTP 接口，请使用支持该场景的部署方式。
- `github.io` 在国内的访问稳定性通常不如当前 `app.workbuddy.host` 域名。
