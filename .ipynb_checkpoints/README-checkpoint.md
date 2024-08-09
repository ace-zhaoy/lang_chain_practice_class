# 介绍
这是 「LangChain实战课」 部分示例，针对已经废弃的、不能运行的代码做了改动。

# 环境
Win11 WSL2、Docker jupyterLib（基于nvidia/cuda:12.3.2-cudnn9-runtime-ubuntu22.04镜像构建的）、NVIDIA GeForce RTX 3080 Laptop GPU (16 GB)

# 主要修改
#### 06｜调用模型：使用OpenAIAPI还是微调开源Llama2-ChatGLM
1. 增加 Qwen 官网例子，并调整代码，使其能在 16GB 内存的 GPU 上运行
2. 模型换成 meta-llama/Meta-Llama-3-8B 和 Qwen/Qwen2-7B-Instruct
3. 调整部分已经废弃或快废弃的代码
4. LangChain 调用自定义语言模型换成 qwen2-7b-instruct-q5_k_m.gguf

#### 07｜输出解析：用OutputParser生成鲜花推荐列表
1. 调整 OpenAI 的引入和调用 （langchain_openai）
2. 模型换成 gpt-4o-ca

#### 08｜链（上）：写一篇完美鲜花推文？用SequencialChain链接不同 的组件
1. 调整 langchain 调用
2. 调整顺序链 SequentialChain

#### 09｜链（下）：想学“育花”还是“插花”？用RouterChain确定客户意 图
1. 简化 MultiPromptChain 调用

#### 10｜记忆：通过Memory记住客户上次买花时的对话细节
1. 调整一些代码细节

#### 11｜代理（上）：ReAct框架，推理与行动的协同
1. 将即将废弃的 initialize_agent 换成 create_react_agent

#### 13｜代理（下）：结构化工具对话、Self-Ask with Search以及 Plan and execute代理
1. 修改 Playwright 测试网页代码，支持在没有图形界面的环境中运行（docker 中的 jupyterLab）
2. 修改 create_async_playwright_browser 的引入，从 langchain_community.tools.playwright.utils 引入
3. 修改 PlayWrightBrowserToolkit 代理调用，支持在 jupyterLab 中运行
4. 将 initialize_agent 修改为 create_structured_chat_agent
