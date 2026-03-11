# claude-code-skills

Shareable skills for Claude Code — drop them into any project and run them as slash commands.

These are thinking tools and self-knowledge tools, not project-specific helpers. They're designed to be useful regardless of what you're working on.

---

## Skills

### `/profile-builder` — Teach Claude who you are

A conversational interview that builds a structured self-profile: how you think, how you work, what you know, and how you want to be supported. The output is a `USER_PROFILE.md` you can feed into any Claude Code project so it understands you from the start.

Works for anyone. The more honestly you answer, the more useful the profile.

**Use it when:** Starting a new project. Feeling like Claude doesn't quite get you. Onboarding a new AI tool. Giving the file to a friend to bootstrap their own setup.

---

### `/six-hats` — Explore any topic through six lenses

Based on Edward de Bono's Six Thinking Hats. Start with a topic conversation, then choose one lens or all six:

| Lens | Focus |
|------|-------|
| ⚪ White | Facts & data — what do we actually know? |
| 🔴 Red | Feelings — what's the emotional landscape? |
| 🟢 Green | Analogy & reframe — what does this look like sideways? |
| 🟡 Yellow | Value & opportunity — why does this matter? |
| ⚫ Black | Misconceptions & failure modes — where does thinking go wrong? |
| 🔵 Blue | Mental model — how should you organize your thinking? |

**Use it when:** Learning something new. Making a decision. Stress-testing a belief. Getting unstuck on a problem. Understanding something from multiple angles at once.

---

## Installation

1. Copy the `.md` file(s) into your project's `.claude/commands/` directory:

```bash
mkdir -p .claude/commands
cp profile-builder.md .claude/commands/
cp six-hats.md .claude/commands/
```

2. In Claude Code, run the skill:

```
/profile-builder
/six-hats
/six-hats quantum entanglement
/six-hats should I take this job offer
```

That's it. Skills are plain markdown — no dependencies, no setup beyond dropping the file in the right place.

---

## Using Your Profile

After running `/profile-builder`, you'll have a `USER_PROFILE.md`. To make Claude use it in future sessions, add this to your project's `CLAUDE.md`:

```markdown
See USER_PROFILE.md for context on how to work with me.
```

Or paste the profile contents directly into your project instructions.

---

## Contributing

These are starting points, not finished products. Fork, adapt, improve. If you build something useful, open a PR.

---

Built by [Collin](https://github.com/cbt-dsotm) with Claude Code.
