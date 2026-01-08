---
slug: vscode使用ollama本地模型
title: vscode使用ollama本地模型
authors: [singi]
tags: [vscode, Continue, Ollama, OpenRouter]
---

- 在 `vscode` 里面安装 `Continue` 插件
- 安装 `Ollama`，并安装本地模型，启动服务
- 注册 `OpenRouter`，获取 `API Key`
- 配置 `Continue` 插件

<!-- truncate -->

> `OpenRouter`模型列表中搜索 [`free`](https://openrouter.ai/models?q=free) 可以使用免费的模型，按照下面的 `xiaomi/mimo-v2-flash:free` 配置使用。

```yml
name: Local Config
version: 1.0.0
schema: v1
models:
  - name: Qwen2.5-Coder 1.5B
    provider: ollama
    model: qwen2.5-coder:1.5b-base
    roles:
      - autocomplete
  - name: xiaomi/mimo-v2-flash:free
    provider: openai
    model: xiaomi/mimo-v2-flash:free
    roles:
      - chat
      - autocomplete
      - edit
      - apply
      - embed
      - rerank
    apiBase: https://openrouter.ai/api/v1
    apiKey: sk-or-v1-9f272fe29885decee6f450114949dcb7a8548faf3b0068892b00c528d163c6xx

```
