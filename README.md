# 🧬 Omni-Vibe OS Ultra

> **A Self-Evolving, Hybrid-Architecture E-commerce & Cognitive Operating System.**
>
> 一个基于混合架构（本地 RTX 5070 + 云端 API）的自进化全栈商业与认知操作系统。

![Status](https://img.shields.io/badge/Status-Active_Development-green)
![Backend](https://img.shields.io/badge/Backend-FastAPI-blue)
![Frontend](https://img.shields.io/badge/Frontend-Next.js_14-black)
![AI](https://img.shields.io/badge/AI-LangGraph_%7C_GraphRAG-purple)
![Local Compute](https://img.shields.io/badge/Local-RTX_5070-76b900)

## 📖 简介 (Introduction)

**Omni-Vibe OS Ultra** 是专为技术型电商创业者设计的超级自动化系统。它不仅仅是一个工具集，而是一个具备**“思考-执行-进化”**闭环的数字生命体。

核心理念：
1.  **Hybrid Compute**: 本地显卡负责高吞吐任务（生图/OCR），云端 API 负责高智商推理。
2.  **Agentic Workflow**: 引入 LangGraph，从线性执行进化为“生成-审查-修正”的智能体循环。
3.  **Active Learning**: 夜间自动利用用户反馈数据微调本地模型，越用越顺手。

## 🏗️ 系统架构 (Architecture)

系统采用 **Modular Monolith (模块化单体)** 架构，包含三个核心闭环：

```mermaid
graph TD
    User((User)) <--> Frontend[Next.js Dashboard]
    Frontend <--> Backend[FastAPI Gateway]

    subgraph "思考环 (Thinking Loop)"
        Orchestrator[LangGraph Controller]
        Critic[Reviewer Agent]
        Researcher[GraphRAG Engine]
    end

    subgraph "执行环 (Execution Loop)"
        Cloud_API[Cloud APIs (Gemini/OpenAI)]
        Local_Inference[Local Docker (ComfyUI / Ollama)]
        DB[(PostgreSQL + Vector)]
    end

    subgraph "进化环 (Evolution Loop)"
        Feedback[Feedback Logs]
        Trainer[LLaMA-Factory (Nightly Job)]
        Model_Registry[LoRA Adapters]
    end

    Backend --> Orchestrator
    Orchestrator -- "Plan & Critique" --> Critic
    Orchestrator -- "Query Insights" --> Researcher
    Orchestrator -- "Generate Assets" --> Local_Inference
    
    User -- "Rate & Edit" --> Feedback
    Feedback -- "Fine-tune" --> Trainer
    Trainer -- "Update Weights" --> Local_Inference
🧩 核心模组 (Modules)
1. 🟢 全域情报 (Market Intelligence)
抗干扰爬虫: 基于 DrissionPage，突破主流电商平台反爬。
深度洞察: 利用 GraphRAG 分析海量评论，提取隐性关联（如：口味变化 -> 健康趋势）。
2. 🟡 内容工厂 (Content Factory)
混合视觉引擎: 本地 ComfyUI (构图) + 云端 Midjourney (重绘)。
智能体闭环: Generate -> Critique -> Refine 循环，自动修正手指错误或乱码。
视频流水线: 脚本 -> 视频 (Kling) -> 剪辑 (FFmpeg)。
3. 🔵 运营中台 (Ops Assistant)
RPA 机器人: 自动改价、自动回复。
私域自动化: 基于 Wechaty 的社群管理。
4. 🟣 第二大脑 (Second Brain)
万能解析: 本地 OCR + Whisper V3 + PDF 解析。
主动学习: 夜间自动微调本地 Qwen2.5 模型，固化你的文案风格。
📂 目录结构 (Directory Structure)
code
Text
/omni-vibe-os
├── /frontend               # [Next.js] 用户界面
│   ├── /app                # App Router
│   └── /components         # Shadcn UI 组件
├── /backend                # [FastAPI] 核心业务逻辑
│   ├── /app
│   │   ├── /core           # 配置与数据库
│   │   ├── /graph          # GraphRAG 索引与查询
│   │   ├── /workflows      # LangGraph 智能体流
│   │   ├── /training       # LoRA 训练触发器
│   │   └── /modules        # 业务模块 (Market, Content, Ops)
│   └── /services           # 第三方服务封装
├── /local_services         # [Docker] 本地微服务
│   ├── /comfyui            # AI 绘图
│   ├── /ollama             # 本地推理
│   └── /llama_factory      # 微调训练
└── docker-compose.yml      # 一键启动基础设施

🚀 快速开始 (Getting Started)
启动基础设施: docker-compose up -d
启动后端: cd backend && uvicorn app.main:app --reload
启动前端: cd frontend && npm run dev