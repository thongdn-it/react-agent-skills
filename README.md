# React Agent Skills

[![GitHub](https://img.shields.io/badge/GitHub-thongdn--it%2Freact--agent--skills-blue)](https://github.com/thongdn-it/react-agent-skills)

> A comprehensive collection of AI Agent skills optimized for React ecosystem and modern frameworks.

## 📋 Introduction

**React Agent Skills** is a repository that aggregates best practices, guidelines, and patterns structured as "skills" that can be utilized by AI Agents (such as GitHub Copilot, Cursor AI, etc.) to improve code quality when working with React and related technologies.

This repository includes detailed skills for:

- ⚡️ **Next.js 16 App Router** - Performance optimization, caching strategies, server components
- 🎨 **ShadCN UI** - Component patterns, accessibility, theming
- 🎯 **Tailwind CSS** - Utility-first CSS patterns, responsive design
- 🔄 **TanStack Query** - Data fetching, caching, mutations
- 📘 **TypeScript** - Type system optimization, compiler configuration
- 🧪 **Vitest** - Testing patterns, mocking, async testing
- 🏗️ **Vercel Patterns** - Composition patterns, React best practices
- 🎭 **Web Design Guidelines** - UI/UX best practices

## 🚀 Installation

### Requirements

- Node.js 16+ or higher
- npm, yarn, or pnpm

### Using with Agent Skills CLI

The simplest way to use these skills is through the Agent Skills CLI:

```bash
npx skills add https://github.com/thongdn-it/react-agent-skills
```

### Clone Repository

If you want to customize or contribute:

```bash
git clone https://github.com/thongdn-it/react-agent-skills.git
cd react-agent-skills
```

## 📖 Project Structure

```
react-agent-skills/
├── README.md
└── skills/
    ├── nextjs/                      # Next.js 16 App Router
    │   ├── SKILL.md                 # Skill description and rules
    │   ├── AGENTS.md                # Guidelines for agents
    │   ├── assets/                  # Templates and examples
    │   └── references/              # 40+ detailed rules
    │
    ├── shadcn/                      # ShadCN UI
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   └── references/              # Component patterns
    │
    ├── tailwind/                    # Tailwind CSS
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   └── references/              # CSS patterns
    │
    ├── tanstack-query/              # TanStack Query
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   └── references/              # Data fetching patterns
    │
    ├── typescript/                  # TypeScript
    │   ├── SKILL.md
    │   └── references/              # 42+ optimization rules
    │
    ├── vitest/                      # Vitest Testing
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   ├── CHANGELOG.md
    │   └── references/              # 44+ testing patterns
    │
    ├── vercel-composition-patterns/ # Vercel Composition Patterns
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   └── rules/
    │
    ├── vercel-react-best-practices/ # React Best Practices
    │   ├── SKILL.md
    │   ├── AGENTS.md
    │   └── rules/
    │
    └── web-design-guidelines/       # Web Design
        └── SKILL.md
```

## 💡 Usage

### With AI Coding Assistants

#### GitHub Copilot / Cursor AI

1. **Add skills to your project:**

   ```bash
   npx skills add https://github.com/thongdn-it/react-agent-skills
   ```

2. **AI agent will automatically detect context** when you:
   - Work with Next.js files
   - Write TypeScript code
   - Create components with ShadCN
   - Write tests with Vitest
   - etc.

3. **Skills will be automatically applied** to:
   - Suggest best practices
   - Optimize performance
   - Fix common mistakes
   - Generate better code

#### Manual Reference

You can also directly reference the files to understand best practices:

```bash
# View Next.js rules list
cat skills/nextjs/SKILL.md

# Read a specific rule
cat skills/nextjs/references/cache-use-cache-directive.md

# View TypeScript patterns
cat skills/typescript/SKILL.md
```

### Example Scenarios

#### Scenario 1: Optimize Next.js App Router

```typescript
// ❌ Before (not optimized)
async function getData() {
  const res = await fetch("https://api.example.com/data");
  return res.json();
}

// ✅ After (with skills applied)
import { unstable_cache } from "next/cache";

const getData = unstable_cache(
  async () => {
    const res = await fetch("https://api.example.com/data");
    return res.json();
  },
  ["data-cache-key"],
  {
    revalidate: 3600,
    tags: ["data"],
  },
);
```

#### Scenario 2: TypeScript Performance

```typescript
// ❌ Before (slow type checking)
function process(data: any) {
  return data.map((item: any) => item.value);
}

// ✅ After (with explicit types)
interface DataItem {
  value: string;
}

function process(data: DataItem[]): string[] {
  return data.map((item) => item.value);
}
```

#### Scenario 3: Vitest Testing

```typescript
// ❌ Before (flaky test)
test("loads data", () => {
  const data = loadData();
  expect(data).toBeDefined();
});

// ✅ After (with async patterns)
test("loads data", async () => {
  const data = await loadData();
  expect(data).toBeDefined();
  await vi.waitFor(() => {
    expect(data.status).toBe("ready");
  });
});
```

## 📚 Skills List

### 1. Next.js 16 App Router

- **Scope:** Performance optimization, caching, server components
- **Rules:** 40+ rules divided into 8 categories
- **Priority:** Build optimization, caching, server components
- **File:** [skills/nextjs/SKILL.md](skills/nextjs/SKILL.md)

### 2. ShadCN UI

- **Scope:** Component patterns, accessibility, theming
- **Categories:** Architecture, accessibility, theming, forms
- **File:** [skills/shadcn/SKILL.md](skills/shadcn/SKILL.md)

### 3. Tailwind CSS

- **Scope:** Utility-first CSS, responsive design, optimization
- **File:** [skills/tailwind/SKILL.md](skills/tailwind/SKILL.md)

### 4. TanStack Query

- **Scope:** Data fetching, caching, mutations, optimistic updates
- **File:** [skills/tanstack-query/SKILL.md](skills/tanstack-query/SKILL.md)

### 5. TypeScript

- **Scope:** Type system, compiler config, async patterns
- **Rules:** 42+ optimization rules for compilation and type checking
- **File:** [skills/typescript/SKILL.md](skills/typescript/SKILL.md)

### 6. Vitest

- **Scope:** Testing patterns, mocking, async testing
- **Rules:** 44+ testing best practices
- **File:** [skills/vitest/SKILL.md](skills/vitest/SKILL.md)

### 7. Vercel Patterns

- **Scope:** Composition patterns, React best practices
- **Files:**
  - [skills/vercel-composition-patterns/SKILL.md](skills/vercel-composition-patterns/SKILL.md)
  - [skills/vercel-react-best-practices/SKILL.md](skills/vercel-react-best-practices/SKILL.md)

### 8. Web Design Guidelines

- **Scope:** UI/UX patterns, design principles
- **File:** [skills/web-design-guidelines/SKILL.md](skills/web-design-guidelines/SKILL.md)

## 🎯 Key Features

### Prioritized by Impact

Each skill is organized by priority level:

- **CRITICAL** - Major impact on performance/functionality
- **HIGH** - Significant improvements
- **MEDIUM** - Important best practices
- **LOW** - Minor optimizations

### Category-based Organization

Rules are grouped by topic:

```
nextjs/
  └─ references/
      ├─ build-*.md         (Bundle optimization)
      ├─ cache-*.md         (Caching strategies)
      ├─ server-*.md        (Server components)
      ├─ action-*.md        (Server actions)
      └─ client-*.md        (Client components)
```

### Actionable Guidelines

Each rule includes:

- ✅ **DO** - Best practices with code examples
- ❌ **DON'T** - Anti-patterns to avoid
- 📝 **Why** - Explanation of reasoning
- 🔧 **How** - Implementation guide

## 🤝 Contributing

We welcome all contributions! If you have:

- 🐛 Bug reports
- 💡 Feature requests
- 📝 Documentation improvements
- ✨ New skill suggestions

### Contribution Process

1. **Fork the repository**
2. **Create a new branch:**

   ```bash
   git checkout -b feature/your-skill-name
   ```

3. **Add your skill:**

   ```
   skills/your-skill/
   ├── SKILL.md          # Description and index
   ├── AGENTS.md         # Guidelines for agents
   └── references/       # Detailed rules
       ├── rule-01.md
       └── rule-02.md
   ```

4. **Commit changes:**

   ```bash
   git commit -m "feat: add [skill-name] skill"
   ```

5. **Push and create Pull Request:**
   ```bash
   git push origin feature/your-skill-name
   ```

### Guidelines for Contributors

- Follow the existing project structure
- Each rule should have clear code examples
- Add priority level for each rule
- Document "When to Apply" and "When NOT to Apply"
- Include measurable impact when possible

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Credits & Acknowledgments

This project is built upon the excellent work of many talented developers and communities. We are grateful for their contributions to the open-source ecosystem.

### Primary Sources

All skills in this repository are sourced from [skills.sh](https://skills.sh/) - a collection of agent skills for AI-powered development tools.

#### From [Vercel Agent Skills](https://github.com/vercel-labs/agent-skills)

Created and maintained by [Vercel Labs](https://vercel.com/labs)

- **web-design-guidelines** - UI/UX design principles and best practices
- **vercel-composition-patterns** - React composition patterns
- **vercel-react-best-practices** - React best practices and patterns

Special thanks to the Vercel team for pioneering the agent skills framework and their continuous contributions to the developer ecosystem.

#### From [dot-skills by @pproenca](https://github.com/pproenca/dot-skills)

Created and maintained by [Pedro Proença](https://github.com/pproenca)

- **nextjs** - Next.js 16 App Router performance optimization (40+ rules)
- **typescript** - TypeScript performance optimization (42+ rules)
- **vitest** - Vitest testing patterns and best practices (44+ rules)
- **shadcn** - ShadCN UI component patterns and accessibility
- **tailwind** - Tailwind CSS utility-first patterns
- **tanstack-query** - TanStack Query data fetching and caching

Huge thanks to Pedro Proença for the comprehensive and well-structured skill collections that form the core of this repository.

### Original Documentation Sources

The skills are based on official documentation and community best practices from:

- **[Next.js](https://nextjs.org/docs)** by Vercel
- **[TypeScript](https://www.typescriptlang.org/docs/)** by Microsoft
- **[React](https://react.dev/)** by Meta/React Team
- **[Vitest](https://vitest.dev/)** by Vitest Team
- **[ShadCN UI](https://ui.shadcn.com/)** by [@shadcn](https://github.com/shadcn)
- **[TanStack Query](https://tanstack.com/query)** by Tanner Linsley & TanStack Team
- **[Tailwind CSS](https://tailwindcss.com/)** by Tailwind Labs

### Community Contributors

Special thanks to all the developers, maintainers, and contributors who have shared their knowledge and best practices through:

- Blog posts and tutorials
- GitHub discussions and issues
- Conference talks and workshops
- Open-source projects and examples

### Maintainer

This curated collection is maintained by [@thongdn-it](https://github.com/thongdn-it) with the goal of making these best practices more accessible to AI-powered development tools.

---

**Note:** If you are an original author of any content used here and would like attribution, corrections, or removal, please [open an issue](https://github.com/thongdn-it/react-agent-skills/issues) or contact us directly.

## 📞 Contact

- **GitHub:** [@thongdn-it](https://github.com/thongdn-it)
- **Repository:** [react-agent-skills](https://github.com/thongdn-it/react-agent-skills)

---

⭐️ If you find this project helpful, don't forget to star the repository!

**Built with ❤️ for the React & AI community**
