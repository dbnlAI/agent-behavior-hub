# Agent Behavior Hub

The source code for [The Complete Guide to AI Agent Behavior](https://www.distributional.com/resources/agent-behavior-hub) — a content hub by [Distributional](https://www.distributional.com) covering behavioral signal discovery in production AI systems.

## What This Is

A single-page React application embedded on distributional.com. It contains 15 long-form articles organized across four categories:

- **Context** — How agent observability differs from traditional observability, how logging changes with traces, whether monitoring shifts with agents, and what questions agent analytics can answer
- **Foundation** — The basics of agent behavior, making the case for behavioral signals, and why behavioral signals matter for product improvement
- **Practice** — Real examples of behavioral signals in production, how to build an AI data flywheel, and the missing layer in your observability stack
- **Implementation** — The open AI observability stack, the agent analytics workflow, and guidance for debugging common issues

## Live Site

[distributional.com/resources/agent-behavior-hub](https://www.distributional.com/resources/agent-behavior-hub)

## Tech Stack

- React 18 (bundled)
- Webpack 5
- Babel
- Deployed via Webflow custom code injection
- Served via jsDelivr CDN

## Repository Structure

```
agent-behavior-hub/
└── bundle.js    # Compiled, production-ready bundle — embed this
```

The source JSX lives in a separate internal repository. This repo serves as the CDN host for the compiled bundle.

## Embedding

The hub is embedded on Webflow using a custom code block. The full embed snippet:

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,400;0,500;1,400;1,500&family=DM+Sans:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet" />
<style>
  html, body { margin: 0; padding: 0; background: #0f0f0e; }
  #root { width: 100%; background: #0f0f0e; }
</style>
<div id="root"></div>
<script src="https://cdn.jsdelivr.net/gh/dbnlAI/agent-behavior-hub@COMMIT_SHA/bundle.js"></script>
```

Replace `COMMIT_SHA` with the full SHA of the latest commit in this repo.

## Updating the Hub

When content changes are made:

1. A new `bundle.js` is compiled from the source
2. Upload the new `bundle.js` to this repo
3. Copy the new commit SHA from GitHub
4. Update `COMMIT_SHA` in the Webflow custom code block
5. Save and publish in Webflow

jsDelivr caches aggressively by branch name, so always use the full commit SHA in the embed URL rather than `@main` to guarantee the latest bundle is served.

## About Distributional

[Distributional](https://www.distributional.com) builds DBNL, an adaptive analytics platform that discovers behavioral signals in production AI trace data. Free to deploy, OTEL-native, runs in your own environment.

- Docs: [docs.dbnl.com](https://docs.dbnl.com)
- Quick start: [docs.dbnl.com/get-started/quickstart](https://docs.dbnl.com/get-started/quickstart)
- Hosted: [app.dbnl.com](https://app.dbnl.com)
