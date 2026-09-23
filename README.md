<div align="center">

  <img src="https://raw.githubusercontent.com/routecraftjs/routecraft/main/routecraft.svg" alt="Routecraft" width="120" />

  <h1>Awesome Routecraft <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome" /></a></h1>

  <p><strong>Tools for agents. Or the agent harness itself.</strong></p>

  <p>A curated list of resources for <a href="https://routecraft.dev">Routecraft</a>, the type-safe framework for AI automation. Build the tools an agent uses, or the agent itself, with the same fluent DSL.</p>

</div>

## Contents

- [Official resources](#official-resources)
- [Getting started](#getting-started)
- [Starters](#starters)
- [What is new in 0.7.0](#what-is-new-in-070)
- [Packages](#packages)
- [Tooling](#tooling)

## Official resources

- [Routecraft](https://github.com/routecraftjs/routecraft) - The core framework, monorepo, and documentation source.
- [Documentation](https://routecraft.dev) - Guides, reference, and examples.
- [Blog](https://routecraft.dev/blog/) - Articles and release notes.
- [Changelog](https://routecraft.dev/changelog/) - What landed in each release, including what is still in development.

## Getting started

Two one-liners, and they produce different things.

```bash
bunx create-routecraft
```

Scaffolds an empty project: one capability, the project layout, and nothing else.

```bash
bunx create-routecraft my-agent --example https://github.com/routecraftjs/craft-harness
```

Scaffolds from a public GitHub repository instead of the built-in template. Add
`/tree/<branch>` or `/tree/<branch>/<subpath>` for a branch or a subdirectory.
The repository's files win over the base scaffold, its manifest dependencies and
scripts merge into the base one, and `node_modules`, `.git`, lockfiles and
`.github/workflows` are never copied. Every `@routecraft/*` dependency is set
to the scaffolder's own release, which `bunx` resolves to the latest one.

- [Installation](https://routecraft.dev/docs/introduction/installation/) - Requirements and the supported package managers.
- [Project structure](https://routecraft.dev/docs/introduction/project-structure/) - The folder convention `craft start` discovers.

## Starters

- [craft-harness](https://github.com/routecraftjs/craft-harness) - An agent harness you own: chat, a sandboxed shell, web fetch and search, a workspace, memory, a scheduler, and human approvals, each an ordinary route in `capabilities/`. Scaffold from it with the `--example` line above.
- [craft-playground](https://github.com/routecraftjs/craft-playground) - Run Routecraft in your browser, no install required: a small tour of capabilities, including an authenticated MCP server you can call from any MCP client.
- [Examples](https://github.com/routecraftjs/routecraft/tree/main/examples) - Runnable example capabilities in the main repository.

## What is new in 0.7.0

0.7.0 is the current release. The [changelog](https://routecraft.dev/changelog/#v0-7-0-pre-release)
lists every change, and the [0.6 to 0.7 migration guide](https://routecraft.dev/docs/migrating/0.6-to-0.7/)
covers every upgrade step.

- [Deferral](https://routecraft.dev/docs/reference/operations/defer/) - `.defer()` parks an exchange and `.resume()` brings it back, so a human approval or a slow upstream is a durable state rather than a held connection.
- [Talk to a route from your editor](https://routecraft.dev/docs/advanced/talk-from-your-editor/) - An editor speaking the Agent Client Protocol reaches an agent through a route the app wrote, so the route's own `.authorize()`, `.input()` and `.throttle()` apply per message.
- [The ops plugin](https://routecraft.dev/docs/reference/plugins/opsplugin/) - A management surface over HTTP with three separately gated tiers: introspection lists what an instance exposes, dispatch sends a route an exchange, and events tails the context bus as Server-Sent Events. Health is served beside them, and every tier defaults to off.
- [`craft start`](https://routecraft.dev/docs/reference/cli/#start) - A project is a folder convention (`capabilities/`, `plugins/`, `agents/`, `skills/`) rather than a single file handed to `craft run`.

## Packages

- [`@routecraft/routecraft`](https://www.npmjs.com/package/@routecraft/routecraft) - Core library: builder, DSL, context, and adapters.
- [`@routecraft/ai`](https://www.npmjs.com/package/@routecraft/ai) - AI and MCP integrations: LLM, embeddings, agents, and the MCP server/client.
- [`@routecraft/cli`](https://www.npmjs.com/package/@routecraft/cli) - The `craft` CLI for running projects and capabilities.
- [`@routecraft/os`](https://www.npmjs.com/package/@routecraft/os) - System-native host adapters: isolated subprocess execution and browser automation.
- [`@routecraft/testing`](https://www.npmjs.com/package/@routecraft/testing) - Test utilities for capabilities.
- [`@routecraft/eslint-plugin-routecraft`](https://www.npmjs.com/package/@routecraft/eslint-plugin-routecraft) - ESLint rules for authoring capabilities.
- [`@routecraft/prettier-plugin-routecraft`](https://www.npmjs.com/package/@routecraft/prettier-plugin-routecraft) - Prettier plugin that keeps DSL chains compact.
- [`create-routecraft`](https://www.npmjs.com/package/create-routecraft) - Project scaffolder.

## Tooling

- [Agent Skills](https://github.com/routecraftjs/routecraft/tree/main/skills) - Authoring skills for adapters and capabilities, in the open Agent Skills format, so any agent can use them. Install with `bunx skills add routecraftjs/routecraft`.
- [Claude Code plugin](https://github.com/routecraftjs/routecraft/tree/main/.claude-plugin) - The same skills as a plugin: `/plugin marketplace add routecraftjs/routecraft` then `/plugin install routecraft-skills@routecraft`.

## Contributing

Contributions are welcome. Have a Routecraft project, adapter, article, or tutorial to share? Open a pull request and add it to the list. Please keep entries on topic and follow the [awesome list guidelines](https://github.com/sindresorhus/awesome/blob/main/awesome.md).
