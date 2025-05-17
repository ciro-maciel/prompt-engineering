# Prompt Engineering Playbook 📜✨

> **Live site:** [https://your-org.github.io/prompt-engineering](https://your-org.github.io/prompt-engineering)
> Boost your LLM projects with ready‑to‑use prompts, proven design patterns, and evaluation tools (PT‑BR 🇧🇷 & EN 🇬🇧).

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Build](https://img.shields.io/github/actions/workflow/status/your-org/prompt-engineering/ci.yml?branch=main)
![Docs](https://img.shields.io/github/actions/workflow/status/your-org/prompt-engineering/docs.yml?label=docs)

---

## 📌 Why this repo?

Crafting great prompts is half art, half science – and the best examples are scattered across the internet.
This repository collects **battle‑tested prompts**, **explanatory patterns**, and **automation scripts** so you can:

1. **Copy & paste** high‑performing prompts for generation, extraction, classification, and transformation tasks.
2. **Understand** the underlying patterns (*Chain‑of‑Thought*, *ReAct*, *Persona Switching*, etc.).
3. **Evaluate** different models & settings using an open‑source harness wired into CI.
4. **Browse everything online** via a GitHub Pages site with search, sidebars, and versioning.

---

## 🌐 Live Docs on GitHub Pages

The Markdown in this repo is rendered as a static site built with **[Docusaurus 3](https://docusaurus.io/)**.

| Action            | Command              |
| ----------------- | -------------------- |
| Run docs locally  | `bun run docs:dev`   |
| Build static site | `bun run docs:build` |
| Preview build     | `bun run docs:serve` |

A GitHub Action (`.github/workflows/docs.yml`) automatically deploys the `/build` output to the **`gh-pages`** branch after every push to `main`.

> **Tip:** All Markdown under `prompts/`, `patterns/`, and `templates/` is automatically picked up by Docusaurus via `docs/plugin-content-pages`.

---

## 🗂 Repository layout

```text
prompt-engineering/
├─ README.md                ← you are here
├─ CONTRIBUTING.md          ← how to contribute prompts & docs
├─ LICENSE                  ← MIT by default – change if needed
├─ docs/                    ← Docusaurus config & static assets
│  ├─ docusaurus.config.ts
│  └─ sidebar.ts
├─ prompts/                 ← ready‑to‑use prompts (with YAML front‑matter)
│  ├─ generation/
│  ├─ classification/
│  ├─ extraction/
│  └─ transformation/
├─ patterns/                ← conceptual guides & anti‑patterns
├─ templates/               ← blank skeletons to kick‑start new prompts
├─ evals/                   ← evaluation harnesses & metrics
└─ tools/                   ← CLI utilities (index generator, linter, etc.)
```

### Front‑matter convention

Every prompt starts with required **YAML** metadata so scripts can build an index and Docusaurus can create filters:

```yaml
---
title: "LinkedIn Post Generator"
category: generation
tags: [marketing, social-media, portuguese, english]
model: agnostic
temperature: 0.8
author: "Ciro Maciel"
updated: 2025-05-17
description: |
  Generates an engaging LinkedIn post on any topic.
---
```

The prompt body goes below the front‑matter.

---

## 🚀 Quick start

```bash
# 1. Clone the repository
$ git clone https://github.com/your-org/prompt-engineering.git
$ cd prompt-engineering

# 2. Install dependencies (Node ≥18 + bun recommended)
$ bun install        # or npm install / pnpm i

# 3. Serve docs locally (auto‑reload)
$ bun run docs:dev   # then open http://localhost:3000

# 4. Explore prompts in /prompts & /patterns ✨
```

---

## 🧪 Evaluating prompts

Inside **evals/** you’ll find harnesses based on [Promptfoo](https://github.com/sourcegraph/promptfoo) and LangChain benchmarks.
Run `bun run tools/eval --prompt prompts/generation/linkedin_post.md` to compare models and hyper‑parameters.

---

## 🤝 Contributing

We **welcome** pull requests! Please skim **CONTRIBUTING.md**, but in short:

1. Fork → Branch → Add your Markdown under the correct folder.
2. Keep front‑matter complete; run `bun run check` to lint.
3. Commit + open PR.
4. CI will run lint, docs build, and eval smoke‑tests.

Feel free to open issues with questions or suggestions.

---

## 📄 License

Released under the **MIT License** – see `LICENSE`.

---

## ✨ Acknowledgements

* [OpenAI](https://openai.com/) best‑practice research.
* [Bun](https://bun.sh/) for ultra‑fast TypeScript tooling.
* The community of prompt engineers who share their wisdom.

*Happy prompting & see you on the docs site!* 🚀
