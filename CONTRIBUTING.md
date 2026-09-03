# Contributing to Kreflux

Thank you for your interest in contributing to **Kreflux**!

Kreflux is building an open, self-healing substrate for resilient reasoning inference, local-first agentic companions, transparent CoT traces, and community-driven evaluation datasets. We believe that AI inference must be inspectable, reliable, and completely free of proprietary lock-in.

Whether you are fixing a bug, improving documentation, designing benchmarks, or implementing an inference provider adapter, your contributions are welcome.

---

## Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Guiding Principles](#guiding-principles)
3. [Finding Something to Work On](#finding-something-to-work-on)
4. [Branch Conventions](#branch-conventions)
5. [Commit Message Conventions](#commit-message-conventions)
6. [Development Setup & Standards](#development-setup--standards)
   - [Frontend & Full-Stack (Next.js / TypeScript)](#frontend--full-stack-nextjs--typescript)
   - [Inference & Evaluation (Python / PyTorch / vLLM)](#inference--evaluation-python--pytorch--vllm)
   - [Database & Schema Changes (Supabase)](#database--schema-changes-supabase)
7. [Pull Request Process](#pull-request-process)
8. [Code Review Guidelines](#code-review-guidelines)
9. [Reporting Security Issues](#reporting-security-issues)

---

## Code of Conduct

All contributors and maintainers are expected to uphold our [Code of Conduct](./CODE_OF_CONDUCT.md). Please read it before participating in our repositories, issue trackers, and community channels.

---

## Guiding Principles

When contributing to Kreflux repositories, please keep our core tenets in mind:

1. **Full Trace Inspectability**: Never hide or truncate model thinking or system prompts unless explicitly commanded by user configuration. The developer and researcher must always have full visibility into the execution graph.
2. **Resilience & Graceful Failover**: Never assume a single inference provider is permanent. Network dropouts, rate limits, and service failures must be handled transparently through the multi-provider fallback engine.
3. **No Vendor Lock-In**: APIs, wire protocols, and storage formats should remain open, portable, and standard-compliant (OpenAI-compatible SSE, Hugging Face Datasets, Parquet/JSONL).
4. **Accessible Scientific UI**: Real-time streaming rendering must handle markdown, LaTeX formulas (`KaTeX`), and diagrams (`Mermaid`) cleanly without jumping layouts or visual glitches.

---

## Finding Something to Work On

Check our issues across the organization repositories:

- `good first issue`: Ideal starting tasks for new contributors.
- `help wanted`: High-priority items where we actively seek community expertise.
- `rfc` / `proposal`: Architectural design discussions open for feedback.

If you want to propose a substantial architectural change or introduce a new provider integration, please open an **RFC (Request for Comments)** issue first so maintainers and community members can collaborate on the design before code is written.

---

## Branch Conventions

We maintain a clean, predictable branching model across all Kreflux repositories:

- `main`: The production-ready branch. Protected. Only merged via approved Pull Requests with green CI checks.
- `feat/<topic>` or `feature/<topic>`: New features, UI additions, provider integrations.
- `fix/<issue-or-topic>`: Bug fixes, resilience patches, error handling improvements.
- `docs/<topic>`: Documentation updates, architectural diagrams, tutorials.
- `perf/<topic>`: Latency optimizations, token throughput improvements, bundle size reduction.
- `refactor/<topic>`: Code structural changes without modifying functional behavior.
- `test/<topic>`: New automated tests, mock providers, or benchmarking harnesses.

### Example Branch Setup

```bash
git checkout -b feat/featherless-speculative-streaming
```

---

## Commit Message Conventions

We follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification. This ensures automated release notes, clear Git histories, and straightforward changelog generation.

### Commit Format

```text
<type>(<optional scope>): <description>

[optional body]

[optional footer(s)]
```

### Supported Types

- **`feat`**: A new feature or capability.
- **`fix`**: A bug fix or resilience repair.
- **`docs`**: Documentation only changes.
- **`style`**: Changes that do not affect the meaning of the code (formatting, white-space).
- **`refactor`**: A code change that neither fixes a bug nor adds a feature.
- **`perf`**: A code change that improves performance or latency.
- **`test`**: Adding missing tests or correcting existing tests.
- **`build`**: Changes that affect the build system or external dependencies.
- **`ci`**: Changes to CI configuration files and scripts.
- **`chore`**: Other changes that don't modify src or test files.

### Commit Message Examples

```text
feat(router): add adaptive timeout for fallback provider switching
fix(katex): prevent layout jump during streaming latex delimiter parsing
docs(klucid): update CLI device authentication walkthrough
test(eval): add regression test for reasoning rung token bounds
```

---

## Development Setup & Standards

### Frontend & Full-Stack (Next.js / TypeScript)

Our web interfaces (e.g. `kreflux`) are built with **Next.js 16 (App Router)**, **React 19**, and **Tailwind CSS**.

- **Node Version**: Node.js `>= 22.0.0` is required.
- **Strict Typing**: TypeScript code must be strictly typed (`noImplicitAny`, proper nullability checks).
- **Component Design**: UI components should follow our design token conventions (`app/globals.css`), maintaining symmetrical spacing in idle states and smooth transitions in pending/loading states.
- **Verification Commands**:

  ```bash
  npm run dev      # Launch local development server
  npm run lint     # ESLint checks across repository
  npx vitest run   # Run Vitest unit & integration test suites
  npm run build    # Verify production Next.js build
  ```

### Inference & Evaluation (Python / PyTorch / vLLM)

Our reasoning evaluation harness and dataset generation scripts (`openkreflux`) are written in Python:

- **Python Version**: Python `3.10+`.
- **Formatting**: Format with `black` (88 chars) and lint with `ruff`.
- **Typing**: Use PEP 484 type annotations for public APIs.
- **Verification Commands**:

  ```bash
  ruff check .
  black --check .
  pytest tests/
  ```

### Database & Schema Changes (Supabase)

- **Migrations Only**: Schema changes must be written as discrete SQL migration files under `supabase/migrations/`.
- **No Manual Edits**: Never alter database schemas manually in production or staging SQL editors.
- **Row-Level Security (RLS)**: Every new table MUST enable RLS with explicit policies for authenticated and anonymous roles.

---

## Pull Request Process

1. **Fork the Repository**: Clone your fork locally and create a descriptive branch from `main`.
2. **Implement Your Changes**: Keep your changes focused. Avoid bundling unrelated refactors with bug fixes.
3. **Write or Update Tests**: Ensure every bug fix has a reproducing test, and every new feature has unit or integration coverage.
4. **Run Local Verification**:
   - Make sure all linter checks pass (`npm run lint` or `ruff check .`).
   - Make sure all unit and integration tests pass (`npx vitest run` or `pytest`).
   - Make sure the project builds cleanly (`npm run build`).
5. **Open a Pull Request**:
   - Provide a concise title following Conventional Commits.
   - Describe the problem solved and the architectural approach taken.
   - Include before/after screenshots or terminal recordings for visual or interactive changes.
   - Link any relevant issues (e.g., `Fixes #42`).
6. **Address Feedback**: Maintainers will review your PR. Push follow-up commits to your branch as needed. Once approved and CI passes, a maintainer will squash and merge your PR.

---

## Code Review Guidelines

Reviewers evaluate contributions against:

- **Correctness**: Does the code solve the issue accurately without side effects?
- **Resilience**: Are network errors, provider dropouts, and rate limits gracefully intercepted?
- **Security**: Are environment variables, user credentials, and tenant boundaries protected?
- **Performance**: Does the change introduce unnecessary re-renders, token overhead, or latency regressions?
- **Readability & Maintainability**: Is the code modular, self-documenting, and properly typed?

---

## Reporting Security Issues

Please do **NOT** report security vulnerabilities via public GitHub issues. Refer to our [Security Policy](./SECURITY.md) and report security concerns directly to [security@kreflux.com](mailto:security@kreflux.com).

---

Thank you for helping us build the future of open, resilient AI reasoning! 🚀
