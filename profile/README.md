<div align="center">

# Kurenai Studio

### AI-native game creation, built around source code.

**AI 是作者 · 源码是事实 · 引擎是可替换的执行后端**

我们正在构建一套面向 AI 时代的游戏开发工具链：  
AI 直接维护工程源码，引擎专注于资源、编译、运行和结果验证。

[Kurenai Studio](https://github.com/kurenai-studio/kurenai) ·
[技术设计](https://github.com/kurenai-studio/kurenai/blob/main/docs/技术文档.md) ·
[安装方法](https://github.com/kurenai-studio/kurenai/blob/main/docs/安装方法.md)

</div>

---

## What we are building

传统工具让 AI 学习操作编辑器。Kurenai Studio 选择另一条路线：

```text
人的意图
→ AI 理解、规划并修改源码
→ 引擎导入、编译和运行
→ 实时预览与错误反馈
→ AI 继续迭代
```

我们不试图复制一套供 AI 点击的 Hierarchy、Inspector 和菜单系统，而是建立更短、更透明的闭环：

- **Source-first** — 所有有效修改最终固化到工程文件。
- **Engine-light** — 引擎退回为资源编译器、运行时和结果验证器。
- **Agent-native** — 项目上下文、节点选择和运行反馈直接进入 Agent。
- **Asset-independent** — 资源生产独立于具体引擎和供应商。
- **Reproducible** — 修改可比较、可审查、可回滚、可自动验证。

## Projects

### [Kurenai Studio](https://github.com/kurenai-studio/kurenai)

DSH 原生的 Cocos AI 开发工作台。把对话、Headless Cocos 实时预览、节点树和运行时 Inspector 放在同一个界面中。

### [ViewWeaver](https://github.com/kurenai-studio/ViewWeaver)

从 Cocos Prefab 生成强类型 View 绑定，把节点结构转化为 AI 和 TypeScript 可以稳定理解、引用与维护的源码契约。

### [assetsSrcAPI](https://github.com/kurenai-studio/assetsSrcAPI)

AI 时代的数字资产供应链层。统一外部资源来源、内容寻址存储、版权与来源信息，以及面向 Cocos 等执行后端的导入适配。

### [Cocos Inspector](https://github.com/kurenai-studio/CososInspector)

面向 Cocos Creator 2.x/3.x 与 PixiJS 的运行时检查、场景快照和资源导出工具，为 Kurenai 提供项目理解与运行反馈能力。

### [harExplorer](https://github.com/kurenai-studio/harExplorer)

从 HAR 中识别、提取和预览纹理、Spine、位图字体、粒子与音频，为资源研究、迁移和复用提供工具链。

### [baseAIAutoCocos](https://github.com/kurenai-studio/baseAIAutoCocos)

早期 Cocos Creator AI 工具基座，保留传统 Creator 扩展集成路径，并作为架构演进与兼容性参考。

## Architecture

```mermaid
flowchart LR
    H[人的意图] --> A[AI 控制平面]
    A --> S[源码事实层]
    S --> E[引擎执行后端]
    E --> P[实时预览与反馈]
    P --> A
    R[外部资源生产<br/>assetsSrcAPI] --> S
    V[Prefab 强类型绑定<br/>ViewWeaver] --> S
```

引擎仍然负责确定性的资源导入、编译、渲染、运行和构建。  
AI 负责理解意图、修改工程、分析结果并持续迭代。

## Current focus

- 完善 Kurenai 与 DSH 的原生工作流。
- 缩短源码修改到 Headless Cocos 预览之间的反馈时间。
- 将 assetsSrcAPI 接入项目资源生产和导入流程。
- 统一 Cocos Inspector 与 Kurenai 的运行时观察能力。
- 建立可验证、可回滚的源码级 Scene 与 Prefab 修改能力。

## Status

项目仍处于快速演进阶段。接口、工程格式和安装流程可能发生变化，欢迎通过各仓库的 Issues 参与讨论。

<div align="center">

**Build for the AI that is coming, not the editor that is fading.**

</div>
