# Emet Claude Skills

Shared skill library for the emet team. These skills are optimized for frontend, backend, design, and database work.

## Installation

### Option 1: Clone as a Git Submodule (Recommended for teams)

```bash
cd your-project
git submodule add https://github.com/alvaroli01/emet-claude-skills.git .claude/skills/team
```

Then in Claude Code settings, add `.claude/skills/team/*` to your skills path.

### Option 2: Clone Directly

```bash
git clone https://github.com/alvaroli01/emet-claude-skills.git ~/.claude/skills
```

Then restart Claude Code and all skills will be available.

## Available Skills

| Skill | Use When |
|-------|----------|
| **supabase** | Auth, RLS, SSR, Storage, Realtime |
| **supabase-postgres-best-practices** | Tables, columns, migrations, indexes, slow queries |
| **vercel-react-best-practices** | Writing or changing React/Next.js code |
| **vercel-composition-patterns** | Designing reusable components, untangling props |
| **web-design-guidelines** | Reviewing UI: accessibility, UX, dark mode |
| **web-designer** | Creating new pages or visual redesigns |
| **webapp-testing** | Testing app in a real browser, screenshots |
| **model-routing** | Routing tasks to cheaper models when beneficial |
| **skill-creator** | Writing or modifying skills |
| **find-skills** | Finding or installing skills from the ecosystem |

## Usage

Load a skill in Claude Code with:
```
/[skill-name]
```

Or let Claude load it automatically when you mention the topic.

## Updates

To pull the latest skills:
```bash
git pull origin main
# or if using submodule:
git submodule update --remote
```

---

Built for the emet team. Each skill includes its own documentation in `SKILL.md`.
