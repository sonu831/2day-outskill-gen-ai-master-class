# Agentic AI: A Complete Framework

![Agentic AI: A Complete Framework — concentric rings from AI/ML to Agentic AI](../image.png)

A whiteboard map (credit: **Luis Rodrigues**) showing how AI stacks outward from
raw learning to fully automated agentic systems. Each ring adds a capability
layer; the outermost — Agentic AI — automates entire processes.

> Source: whiteboard diagram "Agentic AI: A Complete Framework." The structure
> is reproduced as text below.

## The five layers (inside → out)

| # | Layer | Tagline | What it adds |
|---|-------|---------|--------------|
| 1 | **AI & ML** | Turn your data into decisions | Core learning paradigms |
| 2 | **Deep Learning** | Multi-layered neural networks for complex tasks | Neural architectures |
| 3 | **Gen AI** | Create new content | Content generation + tool use |
| 4 | **AI Agents** | Autonomous tasks | Planning, memory, tool orchestration |
| 5 | **Agentic AI** | Automate entire processes | Long-running, governed, self-recovering automation |

### 1. AI & ML (foundation)

- Natural Language Processing
- Reasoning & Problem Solving
- Supervised Learning
- Reinforcement Learning
- Unsupervised Learning

### 2. Deep Learning

- Attention Mechanisms
- Transfer Learning
- Large Language Models (LLMs)
- Deep Belief Networks
- Recurrent Networks & LSTMs
- Convolutional Neural Networks (CNNs)

### 3. Gen AI

- Personalisation
- Multimodal Generation (text + image + audio)
- Hallucination Mitigation
- Tool Use & Function Calling
- Prompt Engineering
- Retrieval-Augmented Generation (RAG)
- Speech Interfaces (TTS & ASR)
- Audio / Music Generation
- Video Generation
- Image Generation
- Code Generation

### 4. AI Agents

- Agent Coordination & Communication
- Multi-agent Collaboration
- State Persistence
- Planning (ReAct, CoT, ToT)
- Task Scheduling & Prioritization
- Goal Decomposition
- Tool Orchestration (actions / plugins)
- Context Management (state & history)
- Human-in-the-Loop Oversight
- Memory Systems (short-term & long-term)
- Self-reflection & Error Recovery

### 5. Agentic AI

- Rollback Mechanisms
- Feedback Loops & Evaluators
- Cost & Resource Management
- Long-term Autonomy & Goal Chaining
- Governance, Safety & Guardrails
- Memory Governance & Retention Policies
- Observability & Tracing
- Delegation & Handoff Protocol
- Risk Management & Constraints
- Agent Marketplaces & Contracts
- Failure Recovery & Replanning
- Dynamic Tooling
- Autonomous Execution
- Output Validation
- Frameworks & Runtimes

## The journey: Foundation → Full Automation

The diagram's arcs map to maturity rings, inner → outer:

- **Foundation** — AI & ML / Deep Learning (the base)
- **Core Systems** — the engines (Deep Learning / Gen AI)
- **Creation** — Gen AI (make new content)
- **Action** — AI Agents (take autonomous steps)
- **Full Automation** — Agentic AI (run end-to-end processes)

## Top-level capability lists (from the board)

- **Key Technologies:** Attention Mechanisms · Transfer Learning · LLMs ·
  Transformers · CNNs · LSTMs
- **Agent Capabilities:** Agent Protocol · Intent Preservation · Self-improving
  Agents
- **Agent Management:** Task Scheduling · Rollback · Self-Improvement ·
  Feedback Loops

## Where this maps in the repo

- **AI → ML → NN → LLM** lineage:
  [Introduction to Generative AI](../generative-ai/01-introduction.md)
- How LLMs work internally (tokenize → embed → attend → predict):
  [How Language Models Work](../generative-ai/02-how-llms-work.md)
- RAG & context/memory:
  [Context, Memory & Limits](../generative-ai/04-context-and-memory.md)
- Tool use + the agent loop:
  [Tools & Extended Features](../claude/04-tools-and-features.md)
- Skills/SOPs as agent recipes:
  [Skills & SOPs](../claude/06-skills-and-sops.md)
- The AI-fluency ladder (Basic User → AI Generalist):
  [AI Skill Levels](./ai-skill-levels.md)

## Recap

- AI matures outward: **ML → Deep Learning → Gen AI → AI Agents → Agentic AI**.
- Gen AI adds *creation*; Agents add *autonomous action*; Agentic AI adds
  *governed, long-running automation*.
- Each outer ring inherits the inner: no safe agentic AI without solid ML, RAG,
  and planning underneath.

---

**See also:** [AI Tools Demonstrated](./ai-tools.md) ·
[Hands-On Claude](../claude/07-hands-on-claude.md) ·
[Back to README](../README.md)
