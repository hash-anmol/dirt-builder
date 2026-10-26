# DIRT-builder

A skill that turns a one-line dream into a working AI agent. You type a wish, it asks 6 short questions (each with a Recommended answer), writes the agent's `SKILL.md`, runs it safely, and sets up a daily routine so it keeps getting better.

From the talk **"How to do anything with AI agents"** at FallingSun 2026 by [@agenticanmol](https://www.instagram.com/agenticanmol/).

**DIRT** = **D**ream it out · **I** do it myself first · **R**ecord it as a SKILL.md · **T**une it daily.

## Try it in 10 minutes

Read the step-by-step guide: [DIRT-builder-Try-It-Guide.pdf](DIRT-builder-Try-It-Guide.pdf). Session notes: [Anmol-AI-Agents-Session-Notes.pdf](Anmol-AI-Agents-Session-Notes.pdf).

### Method A: any AI chat (easiest)
1. Open [`dirt-builder/SKILL.md`](dirt-builder/SKILL.md) and copy everything.
2. Paste it into a new chat as your first message and send.
3. Send your dream as the second message.

### Method B: Claude app with Skills
Download [`dirt-builder.zip`](dirt-builder.zip), upload it in Claude's Skills settings, then type `/dirt-builder` followed by your dream.

### Method C: Claude Code
```bash
git clone https://github.com/hash-anmol/dirt-builder.git
mkdir -p ~/.claude/skills && cp -r dirt-builder/dirt-builder ~/.claude/skills/
```
Then start Claude Code and type `/dirt-builder` followed by your dream.

## The example dream from the talk

```
/dirt-builder
I wish someone could search for the top companies from Y Combinator. It would then go through all those companies, analyse their current operations and their careers, and filter the relevant companies for my profile. Find their founders, LinkedIn accounts and email IDs, send them connection requests and messages with my job offer, find me a job as a growth marketeer, and update me daily.
```

Answers used in the demo: use my own browser · YC directory + job board · Notion database for the tracker · paste one message in my own voice for tone · approve the morning batch, agent sends · Notion + Gmail for the report. Then say `run`. Tip: tell it you are rehearsing and it runs in demo mode (nothing is sent).

## Safety

The skill drafts first and asks before anything is sent, posted or paid. Keep keys and passwords out of chat and out of commits.

## Questions?

I ran out of time on stage. DM me on Instagram: [@agenticanmol](https://www.instagram.com/agenticanmol/). Built something? Tag me.
