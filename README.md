<h1 align="center">⚛️ React Frontend Skills</h1>

<p align="center">
  <strong>A robust, agent-ready skills collection for the modern React ecosystem — by Pythoughts</strong>
</p>

<p align="center">
  <a href="https://github.com/Pythoughts-labs/react-frontend-skills/stargazers"><img src="https://img.shields.io/github/stars/Pythoughts-labs/react-frontend-skills?style=for-the-badge&logo=github&color=yellow" alt="GitHub Stars" /></a>
  <a href="https://github.com/Pythoughts-labs/react-frontend-skills/network/members"><img src="https://img.shields.io/github/forks/Pythoughts-labs/react-frontend-skills?style=for-the-badge&logo=github&color=blue" alt="GitHub Forks" /></a>
  <a href="https://github.com/Pythoughts-labs/react-frontend-skills/issues"><img src="https://img.shields.io/github/issues/Pythoughts-labs/react-frontend-skills?style=for-the-badge&color=orange" alt="Open Issues" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/Pythoughts-labs/react-frontend-skills?style=for-the-badge&color=green" alt="License" /></a>
</p>

<p align="center">
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-install-per-agent">Per-Agent Install</a> •
  <a href="#-skills-included">Skills</a> •
  <a href="#-why">Why?</a> •
  <a href="#-contributing">Contributing</a>
</p>

---

## 🎯 What is this?

**React Frontend Skills** is a curated collection of **18 production-grade AI agent skills** for the React ecosystem. Drop them into your AI coding assistant and it instantly applies battle-tested best practices for performance, UI, testing, data, and architecture.

Each skill is a portable folder (`SKILL.md` + `AGENTS.md` + `references/`) that follows the open agent-skills convention, so it works across **every major AI coding agent** — no lock-in.

- ⚡ **Performance** — React 19, Next.js 16, concurrent rendering
- 🎨 **UI** — Tailwind CSS v4, shadcn/ui, responsive & accessible design
- 🧪 **Testing** — Vitest, Playwright, TDD, MSW
- 📦 **Data** — TanStack Query, Zod, React Hook Form, nuqs
- 🏗️ **Architecture** — feature-based organization, composition patterns

---

## 🚀 Quick Start

Install everything with one command — it auto-detects the AI agents installed on your machine:

```bash
npx skills add Pythoughts-labs/react-frontend-skills --all
```

Pick specific skills instead:

```bash
npx skills add Pythoughts-labs/react-frontend-skills -s react,nextjs,tailwind
```

Install at the user level (global) so every project sees them:

```bash
npx skills add Pythoughts-labs/react-frontend-skills --all -g
```

> Powered by the open-source `skills` CLI. No account, no config — skills are symlinked into your agent's directory and activate automatically when relevant.

### Or install from npm

Published as [`@pythoughts/react-frontend-skills`](https://www.npmjs.com/package/@pythoughts/react-frontend-skills). Add it as a project dependency, then sync into your agent:

```bash
npm install @pythoughts/react-frontend-skills
npx skills experimental_sync
```

`experimental_sync` reads the package from `node_modules` and installs all 18 skills into your detected agent.

---

## 🤖 Install Per-Agent

Target a single agent with `-a <agent>` (use `-s '*'` for all skills, `-g` for a global install):

| Agent | Command |
| ----- | ------- |
| **Claude Code** | `npx skills add Pythoughts-labs/react-frontend-skills -a claude-code -s '*' -y` |
| **Codex** | `npx skills add Pythoughts-labs/react-frontend-skills -a codex -s '*' -y` |
| **Cursor** | `npx skills add Pythoughts-labs/react-frontend-skills -a cursor -s '*' -y` |
| **OpenCode** | `npx skills add Pythoughts-labs/react-frontend-skills -a opencode -s '*' -y` |
| **Pi** | `npx skills add Pythoughts-labs/react-frontend-skills -a pi -s '*' -y` |
| **Kiro CLI** | `npx skills add Pythoughts-labs/react-frontend-skills -a kiro-cli -s '*' -y` |

<details>
<summary><strong>Pythinker &amp; any other AGENTS.md-aware agent (manual)</strong></summary>

Every skill ships a standard `AGENTS.md`, so any agent that reads agent instructions can consume them directly — no CLI required:

```bash
# Clone once
git clone https://github.com/Pythoughts-labs/react-frontend-skills.git

# Point your agent at the skills directory, or copy what you need
cp -r react-frontend-skills/skills/react   ./.agent/skills/
cp -r react-frontend-skills/skills/nextjs  ./.agent/skills/
```

Then reference a skill from your agent context, e.g. `@skills/react/AGENTS.md`. This is the path for **Pythinker** and any custom in-house agent.

</details>

<details>
<summary><strong>Full list of 60+ supported agents</strong></summary>

The `skills` CLI supports Claude Code, Codex, Cursor, OpenCode, Pi, Kiro CLI, GitHub Copilot, Gemini CLI, Windsurf, Cline, Roo, Goose, Kilo, Droid, Antigravity, Trae, Warp, Zed, Continue, Qwen Code, and many more. Run `npx skills add Pythoughts-labs/react-frontend-skills` with no agent flag to auto-detect yours.

</details>

---

## 📚 Skills Included

### Core Framework

| Skill | Rules | Description |
| ----- | ----- | ----------- |
| ⚛️ [**react**](skills/react) | 40+ | React 19 concurrent rendering, Server Components, hooks optimization |
| 🔺 [**nextjs**](skills/nextjs) | 40+ | Next.js 16 App Router, caching, server components, routing |
| 📘 [**typescript**](skills/typescript) | 42+ | Type system optimization, compiler config, async patterns |

### UI & Styling

| Skill | Rules | Description |
| ----- | ----- | ----------- |
| 🎨 [**tailwind**](skills/tailwind) | 42+ | Tailwind CSS v4 optimization, utility patterns, theming |
| 🧩 [**shadcn**](skills/shadcn) | 42+ | shadcn/ui components, Radix primitives, accessibility |
| 🎭 [**ui-design**](skills/ui-design) | 42+ | UI/UX best practices, accessibility, responsive design |
| 🌐 [**web-design-guidelines**](skills/web-design-guidelines) | 100+ | Comprehensive web design principles |

### Data & State

| Skill | Rules | Description |
| ----- | ----- | ----------- |
| 🔄 [**tanstack-query**](skills/tanstack-query) | 40+ | Data fetching, caching, mutations, optimistic updates |
| 📝 [**react-hook-form**](skills/react-hook-form) | 41+ | Form validation, performance, field arrays |
| ✅ [**zod**](skills/zod) | 43+ | Schema validation, type inference, error handling |
| 🔗 [**nuqs**](skills/nuqs) | 42+ | Type-safe URL query state for Next.js |

### Testing

| Skill | Rules | Description |
| ----- | ----- | ----------- |
| 🧪 [**vitest**](skills/vitest) | 44+ | Testing patterns, mocking, async testing |
| 🎭 [**playwright**](skills/playwright) | 43+ | E2E testing, selectors, authentication, CI |
| 🔌 [**msw**](skills/msw) | 45+ | API mocking with Mock Service Worker |
| 🔴 [**tdd**](skills/tdd) | 42+ | Test-Driven Development methodology |

### Architecture & Best Practices

| Skill | Rules | Description |
| ----- | ----- | ----------- |
| 🏛️ [**feature-arch**](skills/feature-arch) | 42+ | Feature-based architecture, module organization |
| 🧱 [**vercel-composition-patterns**](skills/vercel-composition-patterns) | — | React composition patterns |
| ⚡ [**vercel-react-best-practices**](skills/vercel-react-best-practices) | 57+ | React performance optimization |

---

## 💡 Why

### Expert-level, source-grounded

Every skill is built from official documentation, production-tested patterns, and real-world performance work — not generic advice.

### Prioritized by impact

| Priority | Impact | Description |
| -------- | ------ | ----------- |
| 🔴 **CRITICAL** | Major | Performance issues, build failures |
| 🟠 **HIGH** | Significant | Notable improvements |
| 🟡 **MEDIUM** | Important | Best practices |
| 🟢 **LOW** | Minor | Edge cases, optimizations |

### Actionable, every rule

Each rule includes **DO** (correct pattern + code), **DON'T** (anti-pattern), **WHY** (reasoning), and **HOW** (implementation).

---

## 📁 Project Structure

```
react-frontend-skills/
├── skills/
│   ├── react/                # React 19 patterns
│   ├── nextjs/               # Next.js 16 App Router
│   ├── typescript/           # TypeScript optimization
│   ├── tailwind/             # Tailwind CSS v4
│   ├── shadcn/               # shadcn/ui components
│   ├── tanstack-query/       # Data fetching & caching
│   ├── react-hook-form/      # Form handling
│   ├── zod/                  # Schema validation
│   ├── nuqs/                 # URL state management
│   ├── vitest/               # Unit testing
│   ├── playwright/           # E2E testing
│   ├── msw/                  # API mocking
│   ├── tdd/                  # TDD methodology
│   ├── feature-arch/         # Feature architecture
│   ├── ui-design/            # UI/UX best practices
│   ├── vercel-composition-patterns/
│   ├── vercel-react-best-practices/
│   └── web-design-guidelines/
├── README.md
├── LICENSE
└── CHANGELOG.md
```

Each skill folder contains:

```
skills/<name>/
├── SKILL.md       # Frontmatter + quick reference (what the agent loads)
├── AGENTS.md      # Full agent-facing guide
└── references/    # Detailed rule files
```

---

## 🔧 Usage

Once installed, skills activate automatically when your agent detects a relevant task:

```typescript
// "Create a Next.js page with data fetching"  → nextjs, react, tanstack-query
// "Build a form with validation"              → react-hook-form, zod, shadcn
// "Write tests for this component"            → vitest, tdd, msw
```

Or reference the guidelines directly:

```bash
cat skills/react/SKILL.md
cat skills/nextjs/references/cache-use-cache-directive.md
```

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repo
2. Add a skill folder under `skills/your-skill/` with `SKILL.md`, `AGENTS.md`, and `references/`
3. Open a Pull Request

Improving an existing skill (new rules, fixes, version updates) is just as valuable — open a PR.

---

## 📄 License

MIT © 2026 [Mohamed Elkholy](https://github.com/Pythoughts-labs) — see [LICENSE](LICENSE).

---

<p align="center">
  <strong>Find this useful? ⭐ Star the repo.</strong>
</p>

<p align="center">
  Built and maintained by <strong>Pythoughts</strong> — <a href="https://github.com/Pythoughts-labs">@Pythoughts-labs</a>
</p>
