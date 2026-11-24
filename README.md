<div align="center">

<img src="https://raw.githubusercontent.com/Studio1HQ/Studio1HQ/main/assets/banners/code-reviewer.webp" alt="AI Code Generator and Reviewer on Nebius: Generate and review code with DeepSeek Coder on Nebius AI Studio" width="100%" />

<br />
<br />

# AI Code Generator and Reviewer on Nebius

### Generate and review code with DeepSeek Coder on Nebius AI Studio

A Next.js app called CodePilot that generates code from a prompt and reviews pasted code, using DeepSeek-Coder-V2-Lite-Instruct through the Nebius AI Studio API.

<br />

[![Built by Studio1](https://img.shields.io/badge/Built_by_Studio1-f97316?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxNjAgMTYwIiBmaWxsPSJub25lIj48cGF0aCBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTAgMzVDMCAxNi42ODA3IDE0LjA3NDQgMS42NDg0NCAzMiAwLjEyNjk1M1YxNDFINTEuMDUyM0M1Mi40MzA4IDEzNy4zNDQgNTQuNzQ0NiAxMzMuNjg5IDU3Ljk5MzggMTMwLjAzM0M2MS4xNDQ2IDEyNi41MDggNjQuNjg5MiAxMjMuNDQgNjguNjI3NyAxMjAuODI5QzcyLjU2NjIgMTE4LjM0OSA3Ni4zNTY5IDExNi43ODIgODAgMTE2LjEyOVY4Ni43NTQ0Qzc1LjQ3MDggODcuOTI5MiA3MS4zODQ2IDg5LjY5MTkgNjcuNzQxNSA5Mi4wNDE1QzY0IDk0LjUyMjUgNjAuNzUwOCA5Ny40NiA1Ny45OTM4IDEwMC44NTRDNTYuNTM0NSAxMDIuNzIgNTUuMjU0NSAxMDQuNjU5IDU0LjE1MzkgMTA2LjY3MVYwSDEyNUMxNDQuMzMgMCAxNjAgMTUuNjY5OSAxNjAgMzVWMTI1QzE2MCAxNDQuMzMgMTQ0LjMzIDE2MCAxMjUgMTYwSDEyNFYxOEgxMDQuOTQ4QzEwMy41NjkgMjEuNjgxNiAxMDEuMjU1IDI1LjM2MjggOTguMDA2MiAyOS4wNDQ0Qzk0Ljg1NTQgMzIuNTk0MiA5MS4zMTA4IDM1LjY4NDEgODcuMzcyMyAzOC4zMTRDODMuNDMzOCA0MC44MTIgNzkuNjQzMSA0Mi4zODk2IDc2IDQzLjA0NzRWNzIuNjMwNEM4MC41MjkyIDcxLjQ0NzMgODQuNjE1NCA2OS42NzI0IDg4LjI1ODUgNjcuMzA1N0M5MiA2NC44MDc2IDk1LjI0OTIgNjEuODQ5MSA5OC4wMDYyIDU4LjQzMDdDOTkuNDY1NSA1Ni41NTEzIDEwMC43NDUgNTQuNTk4NiAxMDEuODQ2IDUyLjU3MjNWMTYwSDM1QzE1LjY3IDE2MCAwIDE0NC4zMyAwIDEyNVYzNVoiIGZpbGw9IiNmZmZmZmYiLz48L3N2Zz4K)](https://studio1hq.com)
[![Built with Nebius](https://img.shields.io/badge/Built_with_Nebius-141414?style=for-the-badge)](https://nebius.com)
[![Live demo](https://img.shields.io/badge/Live_demo-1c1917?style=for-the-badge&logo=vercel&logoColor=white)](https://nebius-code-reviewer.vercel.app/)

[Nebius docs](https://docs.tokenfactory.nebius.com) &nbsp;·&nbsp; [Nebius](https://nebius.com) &nbsp;·&nbsp; [More examples](https://github.com/Studio1HQ) &nbsp;·&nbsp; [studio1hq.com](https://studio1hq.com)

</div>

<br />

## Overview

CodePilot is a Next.js app with two modes. In generate mode you describe a problem, pick a language and get code plus an explanation. In review mode you paste a code snippet and some context and get a review back. Both modes call a model hosted on [Nebius AI Studio](https://docs.nebius.com/studio/inference/) through its OpenAI-compatible API.

It is a small reference for adding Nebius-hosted models to a Next.js route handler.

## Features

- **Code generation**: a prompt and a target language return a code block and a written explanation.
- **Code review**: submit a snippet with context and a language to get structured review feedback.
- **JSON responses**: prompts ask the model for a JSON object, which the API routes parse before returning it.
- **Nebius-hosted model**: both routes use `deepseek-ai/DeepSeek-Coder-V2-Lite-Instruct` via the OpenAI SDK pointed at Nebius.
- **Single page UI**: toggle between generate, review and result views from the top bar.

## Tech stack

| Layer | Tool |
| --- | --- |
| Framework | [Next.js](https://nextjs.org) and [React](https://react.dev) |
| LLM | [Nebius AI Studio](https://docs.nebius.com/studio/inference/), DeepSeek-Coder-V2-Lite-Instruct |
| Client | [OpenAI Node SDK](https://github.com/openai/openai-node) with a custom base URL |
| Styling | [Tailwind CSS](https://tailwindcss.com) |
| Deployment | [Vercel](https://vercel.com) |

## Getting started

### Prerequisites

- Node.js 18 or later
- A Nebius AI Studio API key

### Installation

```bash
git clone https://github.com/Studio1HQ/code-reviewer.git
cd code-reviewer
npm install
```

### Environment variables

Copy `env.local.example` to `.env.local` and set:

| Variable | Description |
| --- | --- |
| `NEBIUS_API_KEY` | Nebius AI Studio API key. Create one in the [Nebius Studio inference docs](https://docs.nebius.com/studio/inference/). |

### Run

```bash
npm run dev
```

Open <http://localhost:3000>. A live deployment is at <https://nebius-code-reviewer.vercel.app/>.

## How it works

```text
src/app/
  page.tsx               view switcher: generate, review, result
  components/            GenerateCode, ReviewCode, Result
  api/generate/route.ts  POST: prompt + language -> code and explanation
  api/review/route.ts    POST: context + snippet + language -> review
  util/prompts.ts        prompt templates for both modes
```

Each route builds a prompt from `util/prompts.ts` and calls `client.chat.completions.create` against `https://api.studio.nebius.ai/v1/`. The review route uses temperature 0.3, `max_tokens` 512 and `top_p` 0.95. The response text is matched for a JSON object, parsed, and returned to the client.

## Resources

- [Nebius AI Studio inference docs](https://docs.nebius.com/studio/inference/): API keys and models.
- [Nebius Token Factory docs](https://docs.tokenfactory.nebius.com): current docs for Nebius inference.
- [Nebius](https://nebius.com): the platform site.
- [Live demo](https://nebius-code-reviewer.vercel.app/): deployed app.

<br />

---

<div align="center">

<a href="https://studio1hq.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-dark.svg" />
    <img src="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-light.svg" alt="Studio1" width="160" />
  </picture>
</a>

Built by **[Studio1](https://studio1hq.com)**, the technical content and DevRel partner for devtool teams. Made with [Nebius](https://nebius.com).<br />
Browse more open-source examples at [github.com/Studio1HQ](https://github.com/Studio1HQ).

[![Website](https://img.shields.io/badge/studio1hq.com-0b0807?style=for-the-badge&logo=googlechrome&logoColor=white)](https://studio1hq.com)
[![Book a call](https://img.shields.io/badge/Book_a_strategy_call-f97316?style=for-the-badge&logo=googlecalendar&logoColor=white)](https://cal.com/studio1/collab)
[![X](https://img.shields.io/badge/%40Studio1HQ-141414?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Studio1HQ)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/studio1hq/)

<sub><a href="https://studio1hq.com">studio1hq.com</a> · Technical content, docs, video and DevRel for devtools</sub>

</div>
