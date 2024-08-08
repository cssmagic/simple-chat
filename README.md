# simple-chat

> 一款简单的基于 LLM 的对话机器人，用于演示 LLM 应用开发的基本思路和方法。

## 准备工作

把环境变量文件的模板（`.env.example`）复制一份，命名为真正使用的文件名（`.env`）。

```shell
# Windows
copy .env.example .env

# Linux / macOS
cp .env.example .env
```

编辑 `.env` 文件，填入 LLM API 相关信息。

## 安装依赖

```shell
npm install
```

## 运行开发环境

```shell
npm run dev
```

## 构建生产环境的静态资源

```shell
npm run build
```

