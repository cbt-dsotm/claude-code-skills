# /profile-builder

Help Claude Code learn who I am so it can work with me better — not just smarter, but calibrated to how I actually think.

---

## What This Is

A conversational interview that builds a structured self-profile: how you think, how you work, what you know, and how you want to be supported. The output is a markdown file you can give Claude Code going forward so it understands you from the start of every session.

This works best if you answer honestly and specifically. Vague answers produce generic profiles. The more real you are, the more useful this becomes.

---

## How to Use

Run `/profile-builder` in any Claude Code session. Answer each section honestly. At the end, Claude will write your profile to `USER_PROFILE.md` in your current directory (or wherever you specify).

To use your profile in future sessions: place `USER_PROFILE.md` in your project's `CLAUDE.md` context, or reference it in your project instructions.

---

## The Interview

Conduct this as a conversation, not a form. Work through each section below. Ask one or two questions at a time. Listen to the answers and follow up where something is interesting or unclear before moving on. Don't rush — this is worth doing well.

After all sections are complete, synthesize everything into a structured USER_PROFILE.md and write it to disk. Tell the user where it was saved and how to use it.

---

### Section 1: Who You Are

Start here. Get the basics, then go deeper on anything interesting.

- What's your name?
- What do you do — professionally or otherwise? (Don't need a title, just the real answer.)
- Is there anything about how your brain works that AI should know? Neurotype, learning differences, attention patterns, anything that shapes how you take in information.
- What's your setup? (Main machine, tools you live in, how you work day to day.)

---

### Section 2: How You Think

This is the most important section. Take time here.

- When you're learning something new, what actually works for you? What makes it click?
- What doesn't work — what makes you tune out, get frustrated, or lose the thread?
- Do you tend to start with the big picture and drill down, or build up from specifics? Or something else entirely?
- How do you handle not knowing something? Does uncertainty feel like a problem or an invitation?
- What's your relationship with depth — do you prefer breadth across topics, or do you go deep on fewer things?

---

### Section 3: Working Style

- How do you like to work with an AI? Collaboratively back-and-forth, or give me the answer and get out of the way?
- How long do your focus sessions usually run? Do you have a natural rhythm?
- When you're stuck, what helps most — talking through it, seeing an example, being asked questions, or something else?
- How do you feel about being corrected or pushed back on?

---

### Section 4: Communication Preferences

- What should Claude always do when working with you?
- What should Claude never do?
- How much explanation do you want — concise and direct, or thorough with reasoning?
- Anything about tone — formal, casual, blunt, warm?

---

### Section 5: What You Know

Get a rough knowledge map. This helps Claude calibrate depth and find useful bridges.

- What are the domains where you have deep expertise? (Years in, not just familiarity.)
- What are you actively learning or curious about right now?
- What are the gaps you know about — areas you've avoided or bounced off?
- What are you probably wrong about — beliefs or assumptions you hold but haven't stress-tested?

---

### Section 6: What You're Building or Working Toward

- What's the project or goal this profile is meant to support?
- What does success look like in 6–12 months?
- What's the biggest thing in the way?

---

### Section 7: Anything Else

- Is there anything important that none of the previous questions surfaced?
- Is there anything you want Claude to watch for — patterns in yourself that tend to go sideways?

---

## Output Format

After completing all sections, write `USER_PROFILE.md` to disk with this structure:

```markdown
# USER_PROFILE.md

## 1. Identity & Context
[Name, background, neurotype, setup, context — synthesized from Section 1]

## 2. How I Think
[Processing style, learning approach, relationship with depth and uncertainty — from Section 2]

## 3. Working Style
[Session rhythm, collaboration preference, stuck-state patterns — from Section 3]

## 4. Communication Preferences
[Do/don't, tone, explanation level — from Section 4]

## 5. Knowledge Map
[Expertise, active learning, known gaps, possibly-wrong beliefs — from Section 5]

## 6. Goals & Context
[Current project, success definition, obstacles — from Section 6]

## 7. Watch For
[Patterns, drift tendencies, anything the AI should monitor — from Sections 1 and 7]
```

Write each section as prose or bullets — whatever best captures the person. Do not copy-paste answers verbatim. Synthesize. Make it something Claude would actually find useful, not a transcript.

After writing the file, tell the user:
- Where the file was saved
- How to add it to a project's context (CLAUDE.md or project instructions)
- That they can run `/profile-builder` again any time to update it
