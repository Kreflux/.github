<div align="center">

```text
  ██╗  ██╗██████╗ ███████╗███████╗██╗     ██╗   ██╗██╗  ██╗
  ██║ ██╔╝██╔══██╗██╔════╝██╔════╝██║     ██║   ██║╚██╗██╔╝
  █████╔╝ ██████╔╝█████╗  █████╗  ██║     ██║   ██║ ╚███╔╝ 
  ██╔═██╗ ██╔══██╗██╔══╝  ██╔══╝  ██║     ██║   ██║ ██╔██╗ 
  ██║  ██╗██║  ██║███████╗██║     ███████╗╚██████╔╝██╔╝ ██╗
  ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝     ╚══════╝ ╚═════╝ ╚═╝  ╚═╝
```

### Kreflux — Open Reasoning & Resilient Inference

<p align="center">
  <em>Democratizing high-throughput, multi-provider open reasoning with full trace inspectability and zero vendor lock-in.</em>
</p>

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge&logo=apache)](https://opensource.org/licenses/Apache-2.0)
[![Next.js 16](https://img.shields.io/badge/Next.js-16%20App%20Router-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![HuggingFace Kreflux-AI](https://img.shields.io/badge/HuggingFace-Kreflux--AI-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/Kreflux-AI)
[![Status: Active](https://img.shields.io/badge/Status-Active-22c55e?style=for-the-badge)](https://github.com/Kreflux)

---

[Website](https://kreflux.com) • [Hugging Face](https://huggingface.co/Kreflux-AI) • [Documentation](https://kreflux.com/docs) • [Community](https://github.com/Kreflux) • [Security Policy](https://github.com/Kreflux/.github/blob/main/SECURITY.md)

</div>

---

## 🧭 Manifesto & Vision

Modern AI inference is trapped behind proprietary walls: opaque guardrails, stealth system prompts, silent model degradations, and brittle single-provider dependencies. When inference fails or providers throttle, developers and researchers are left stranded with no fallback and no transparency.

**Kreflux changes the equation.**

We are building an open, self-healing reasoning substrate designed for:

1. **Resilient Multi-Provider Inference**: Zero single points of failure. Inference dynamically fails over across leading providers (Featherless, Neokens, vLLM, OpenRouter) with session resumption and continuous health telemetry.
2. **Full Trace Inspectability**: No censored thinking. Chain-of-thought (CoT) reasoning traces are completely visible, inspectable, and streamable down to individual tokens.
3. **Zero Hidden Prompts**: What you send is what the model sees. Transparent system context with zero proprietary steering or hidden instruction injection.
4. **Research-Grade Open Weights**: We curate and release open datasets, reasoning evaluations, and benchmarks to the global AI research community.

---

## ⚡ Ecosystem Breakdown

Kreflux is structured as a coordinated ecosystem of applications, agentic tools, evaluation frameworks, and open datasets.

```text
                      ┌──────────────────────────────────────┐
                      │            Kreflux Hub               │
                      │        (https://kreflux.com)         │
                      └──────────────────┬───────────────────┘
                                         │
                 ┌───────────────────────┴───────────────────────┐
                 │                                               │
                 ▼                                               ▼
   ┌───────────────────────────┐                   ┌───────────────────────────┐
   │          kreflux          │                   │          klucid           │
   │   Full-stack AI Chat UI   │                   │    CLI Coding Agent       │
   │  Reasoning Ladder (Low    │                   │   Local-first, inspectable│
   │   to Ultra) + KaTeX/Mermaid│                  │   zero hidden prompts     │
   └─────────────┬─────────────┘                   └─────────────┬─────────────┘
                 │                                               │
                 └───────────────────────┬───────────────────────┘
                                         │
                                         ▼
                      ┌──────────────────────────────────────┐
                      │             openkreflux              │
                      │  Multi-Provider Routing Engine       │
                      │  Reasoning Benchmarks & Eval Harness │
                      └──────────────────┬───────────────────┘
                                         │
                                         ▼
                      ┌──────────────────────────────────────┐
                      │         openkreflux-datasets         │
                      │  Curated CoT Reasoning Traces        │
                      │  Hugging Face: hf.co/Kreflux-AI      │
                      └──────────────────────────────────────┘
```

### 1. [`kreflux`](https://github.com/Kreflux/kreflux)

The flagship production AI chat platform.

- **Dynamic Reasoning Ladder**: Dial computational depth from `Low` to `Ultra` on demand.
- **Multi-Provider Failover**: Automatic fallback across Featherless, Neokens, and OpenRouter with resume-on-dropout session persistence.
- **Rich Scientific Rendering**: Real-time streaming markdown, KaTeX math expressions, and interactive Mermaid architectural diagrams.
- **Zero Lock-In**: Full exportability of all conversations, reasoning tokens, and tool calls.

### 2. [`klucid`](https://github.com/Kreflux/klucid)

A local-first, inspectable CLI coding agent and development companion.

- **Zero Hidden System Prompts**: Full auditability over injected system instructions and context windows.
- **Metered Kreflux Compute**: Seamless device auth pairing with the Kreflux backend for shared compute allowances.
- **Transparent Execution**: Interactive approval loops, local file system sandboxing, and live reasoning inspection directly in your terminal.

### 3. [`openkreflux`](https://github.com/Kreflux/openkreflux)

The open reasoning engine and evaluation framework.

- **Multi-Provider Router**: High-throughput routing logic with latency-aware load balancing and synthetic fault-injection testing.
- **Evaluation Harness**: Automated benchmark runner measuring reasoning drift, hallucination indices, and CoT step efficiency.
- **Synthetic Reasoning Pipeline**: Reproducible generation pipeline for multi-step algorithmic and logical reasoning.

### 4. [`openkreflux-datasets`](https://huggingface.co/Kreflux-AI)

Curated high-fidelity Chain-of-Thought (CoT) reasoning traces hosted on Hugging Face.

- **Provenance-Tracked**: Every reasoning trace records generation parameters, base model checkpoints, and step verification.
- **Open-Weight Friendly**: Optimized for fine-tuning open-weight foundation models (Qwen, Llama, DeepSeek) into specialized reasoning architectures.

---

## 🛠️ Technology Stack

| Layer | Technologies | Key Capabilities |
| :--- | :--- | :--- |
| **Frontend & UI** | Next.js 16 (App Router), React 19, Tailwind CSS | Server Components, Edge runtime streaming, accessible design tokens |
| **Math & Visuals** | KaTeX, Rehype/Remark Math, Mermaid.js | High-performance LaTeX formula rendering, dynamic system diagrams |
| **Backend & Auth** | Supabase (PostgreSQL 16), Next.js Route Handlers | Row-Level Security (RLS), custom RPCs, CLI device pairing |
| **Inference Orchestration** | Python 3.10+, vLLM, Featherless, Neokens, OpenRouter | SSE streaming, provider heartbeat checks, latency scoring, fallback |
| **CLI & Tools** | TypeScript, Node.js 22+, Clack, Chalk | Local workspace inspection, terminal streaming, OAuth device flow |

---

## 📦 Repositories Directory

| Repository | Description | Stack | Status |
| :--- | :--- | :--- | :--- |
| [**`kreflux`**](https://github.com/Kreflux/kreflux) | Production web chat platform, multi-provider failover, reasoning ladder | Next.js 16, React 19, Supabase, Tailwind | [![Active](https://img.shields.io/badge/status-active-success)](https://github.com/Kreflux/kreflux) |
| [**`klucid`**](https://github.com/Kreflux/klucid) | Local-first CLI coding agent with inspectable reasoning and device auth | TypeScript, Node.js, CLI | [![Active](https://img.shields.io/badge/status-active-success)](https://github.com/Kreflux/klucid) |
| [**`openkreflux`**](https://github.com/Kreflux/openkreflux) | Open reasoning evaluation framework and routing engine | Python 3.10+, PyTorch, vLLM | [![Active](https://img.shields.io/badge/status-active-success)](https://github.com/Kreflux/openkreflux) |
| [**`openkreflux-datasets`**](https://huggingface.co/Kreflux-AI) | Curated CoT reasoning traces and synthetic instruction sets | Hugging Face Datasets, Parquet, JSONL | [![Datasets](https://img.shields.io/badge/HF-datasets-FFD21E)](https://huggingface.co/Kreflux-AI) |
| [**`.github`**](https://github.com/Kreflux/.github) | Organization profile, community health standards, issue templates | Markdown, GitHub Actions | [![Active](https://img.shields.io/badge/status-active-success)](https://github.com/Kreflux/.github) |

---

## 🚀 Quickstart Guides

### For Developers: Running Kreflux Web Chat

```bash
# Clone the main repository
git clone https://github.com/Kreflux/kreflux.git
cd kreflux

# Install dependencies (requires Node.js >= 22.0.0)
npm install

# Start local development server
npm run dev
```

### For Terminal Users: Klucid CLI Agent

```bash
# Install Klucid globally
npm install -g klucid

# Authorize your device with your Kreflux account
klucid auth login

# Start an interactive, inspectable reasoning session
klucid chat "Analyze src/lib/inference.ts and optimize concurrency"
```

### For Researchers: Exploring Reasoning Traces

```python
from datasets import load_dataset

# Load curated CoT reasoning traces from Hugging Face
dataset = load_dataset("Kreflux-AI/openkreflux-cot-traces", split="train")

# Inspect the first reasoning trace step
sample = dataset[0]
print(f"Prompt: {sample['prompt']}")
print(f"Reasoning Ladder Level: {sample['reasoning_rung']}")
print(f"Full CoT Trace:\n{sample['thinking_trace']}")
```

---

## 🌐 Community & Ecosystem

- 🌐 **Web Platform**: [kreflux.com](https://kreflux.com)
- 🤗 **Hugging Face**: [huggingface.co/Kreflux-AI](https://huggingface.co/Kreflux-AI)
- 🐙 **GitHub**: [github.com/Kreflux](https://github.com/Kreflux)
- 🔒 **Security Disclosures**: [security@kreflux.com](mailto:security@kreflux.com)
- 📜 **Code of Conduct**: [CODE_OF_CONDUCT.md](https://github.com/Kreflux/.github/blob/main/CODE_OF_CONDUCT.md)
- 🤝 **Contributing Guidelines**: [CONTRIBUTING.md](https://github.com/Kreflux/.github/blob/main/CONTRIBUTING.md)

---

<div align="center">
  <sub>Built with precision by the <strong>Kreflux Open Source Initiative</strong>. Open weights, open reasoning, zero vendor lock-in.</sub>
</div>
