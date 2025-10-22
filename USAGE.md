# 使用说明

## 准备环境变量

- 将仓库根目录下的 `.temple.dev.vars` 重命名为 `.dev.vars`（或复制一份保留模板），即可作为本地开发的环境变量文件。
- 根据需要修改其中的 `API_KEY`、各云厂商的 `*_API_KEY` 以及可选的 `CORS_ORIGIN` 等配置项。

## 安装依赖

- 建议使用 `pnpm`，执行 `pnpm install` 安装项目依赖。

## 启动开发服务

- 默认运行：`pnpm dev`，Wrangler 会在 `http://127.0.0.1:8787` 提供本地代理服务。
- 指定端口：
  - 直接传递参数：`pnpm dev -- --port 9000`
  - 或者使用 Wrangler：`wrangler dev src/index.ts --port 9000`
- Ollama 模拟：`pnpm dev:ollama` 会在 `11434` 端口启动，方便与本地 Ollama 客户端兼容。

## 常见操作

- 通过 `pnpm deploy` 将代码部署到 Cloudflare Workers。

完成以上步骤后，本地即可通过 `http://127.0.0.1:<端口>/v1/...` 访问统一的 OpenAI 兼容接口，或根据脚本说明与其他客户端对接。
