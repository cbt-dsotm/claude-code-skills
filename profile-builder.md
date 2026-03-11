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

## Step 0: Check for an Existing Profile

Before starting the interview, search the current directory and common locations for an existing profile file. Look for any of these names (case-insensitive):

- `USER_PROFILE.md`
- `user-profile.md`
- `PROFILE.md`
- `profile.md`
- `ME.md`
- `me.md`
- `ABOUT_ME.md`
- `about-me.md`
- `CLAUDE_PROFILE.md`
- `.claude/profile.md`

Also check whether `CLAUDE.md` contains a profile section (a heading like "About Me", "Who I Am", or "User Profile").

**If no existing profile is found:** proceed directly to the interview (Step 1).

**If an existing profile is found:** show the user the filename and first few lines so they can confirm it's theirs, then ask:

> "I found `[filename]`. What would you like to do?
>
> 1. **Update** — go section by section, keep what's still true, refresh what's changed
> 2. **Merge** — I'll interview you fresh and blend your new answers with the existing content
> 3. **Replace** — start over completely, archive the old file
> 4. **Save as new file** — run fresh and save to a different filename (I'll ask what to call it)"

Then proceed based on their choice:

- **Update** → go to the Update Flow below
- **Merge** → run the full interview (Step 1), then merge results with existing content before writing
- **Replace** → rename the existing file to `[filename].bak` before writing the new one, then run the full interview
- **Save as new file** → ask for the filename, then run the full interview

---

## Update Flow

Used when the user chooses "Update." Do not run the full interview. Instead:

1. Read the existing profile in full.
2. Go through each section one at a time. For each:
   - Summarize what the current profile says about that section in 1–2 sentences.
   - Ask: "Is this still accurate, or has anything changed?"
   - If they say it's fine, keep it as-is.
   - If they have updates, ask follow-up questions to capture what changed, then rewrite just that section.
3. After all sections, ask: "Anything important that wasn't covered in any of those sections?"
4. Write the updated file and tell the user what changed.

---

## The Interview

Conduct this as a conversation, not a form. Work through each section below. Ask one or two questions at a time. Listen to the answers and follow up where something is interesting or unclear before moving on. Don't rush — this is worth doing well.

After all sections are complete, synthesize everything into a structured profile and write it to disk.

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

Write the profile file with this structure:

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
- What mode was used (new / updated / merged / replaced)
- How to add it to a project's context (CLAUDE.md or project instructions)
- That they can run `/profile-builder` again any time to update it
