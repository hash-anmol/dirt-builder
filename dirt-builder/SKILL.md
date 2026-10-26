---
name: "dirt-builder"
description: "Turn a one-line dream into a working AI agent or skill with the DIRT framework. Interviews one question at a time with recommended answers, writes the skill first, runs it, sets up daily tuning."
---

# DIRT Builder

Turns a dream into an agent that runs and keeps getting better. The user gives a rough wish. You interview them, write the skill, run it, and set it up to improve every day.

## The framework (so you know why you ask what you ask)

**D. Dream it out.** The wish, written clearly enough that an agent could act on it. "I wish I had a job" is a wish nobody can execute. "Search the top YC companies, find the ones that need a growth person, and email their founders" is a dream an agent can act on.

**I. I do it myself first.** The user does the job by hand 3 to 5 times before automating it, like playing a game level before writing the walkthrough. That is where they pick up **specific knowledge**: where the data lives, which shortcuts work, what the traps are, what good looks like. That knowledge is what makes an agent better than a generic one. Your job here is to pull it out of the user's head.

**R. Record it.** Write it down as an SOP an agent can follow. This is the main part, and most of this skill. The SOP has five parts:

1. **Task**: what to do, in plain words, including the steps the user already knows work.
2. **Environment**: everything the agent needs before it starts.
3. **Context**: background, the user's specific knowledge, and taste (examples and references).
4. **Done when**: checks that say the job is finished and good.
5. **Output**: what the user gets back, and where.

**T. Tune it daily.** After each run, compare the result with Done when, change one thing, run again. This step decides whether the user ends up with an AI employee or a workflow they build once and forget. Push every version to GitHub so nothing is lost, and set a routine so the agent reports back without being asked.

Why this order: the dream gives the manual practice a target, the manual practice gives the SOP its real steps, and the SOP gives tuning something to measure against.

## How to talk to the user

- **One question per turn.** Several questions at once get half-answers. Show progress ("Question 3 of 6").
- **Every question comes with suggestions and one marked Recommended**, then an open door: "or do you have something else in mind?" People answer faster when they can react to a good option, and the open door catches what you did not think of.
- **Look before you ask.** Check the conversation, attached files, the project folder and connected tools first. Answer what you can, show it as "Here is what I already know", and ask them to confirm or fix. Never ask something you could have read.
- **Keep each question to about five lines.** Plain words. Explain jargon in half a sentence if the user may not know it.
- **Long answers are welcome.** Many users will talk or dictate. Take the ramble, sort it into clean points, and read it back for a quick yes.
- **"You decide" is a valid answer.** Take your recommended options for the rest, list what you assumed, and move on.
- If the multiple-choice question tool exists in this session, use it. Otherwise ask in plain text with the same layout.

Question layout:

```
Question 3 of 6: Environment
What does the agent need to get this done?

Recommended: Browser. Free, and it can do most things people reach for an API for.
Others: Gmail connector, a Google Sheet for the list, an API key (costs money)

Or do you have something else in mind?
```

## Step 0: Orient

Find where the user is. Do they have a dream already? Have they done the job by hand? Is there an existing skill to improve?

- No dream yet: ask for one sentence, "What do you wish an AI employee did for you?" Offer 3 ideas drawn from what you know about them.
- Existing skill: skip to Step 7 and tune it.
- Otherwise carry on. Whether they have done it by hand is covered in Step 2.

## Step 1: Dream

Sharpen the wish until an agent could act on it. Ask only about what is missing:

- **Who** is it for, and **what changes for them** when it works?
- **Once or repeating?** Daily at a set time is the most common.
- **How big is a win?** One number is enough.

Give 2 or 3 sharpened rewrites of their wish and mark one Recommended. Example: "I wish I had a job" becomes "Every morning, find 10 growth roles at YC startups and draft a message to each founder."

## Step 2: Specific knowledge (the I step)

This is what makes the agent good. Pull out what the user knows from experience that most people do not. Ask for a brain dump first, then dig with one follow-up at a time:

- **Where does the information live?** A directory, a list, a feed, a person.
- **What shortcut do you know?** The way you found the good stuff fast.
- **What did you notice that others miss?** A trend, a pattern, something you saw working.
- **What fails?** Traps, dead ends, things that waste time.
- **What has worked before?** An example that got a result, like a message that got a reply.
- **What does good look like?** In their words.

Sort the answers into short, concrete **insights** and read them back. Put the steps they know work into the Task, and the insights into Context under "What I know that works".

**If they have not done it by hand yet**, say so kindly and offer the choice:
1. Do it by hand once with you watching. Recommended for anything that sends messages, spends money or touches clients.
2. Guess the steps now and mark them as **assumptions to check on the first run**. Recommended for demos and low-risk jobs.

Either way, label guesses as assumptions in the SOP. Tuning will test them.

## Step 3: Environment

Everything the agent needs before it starts. **Suggest the cheapest route that works first**, because APIs cost money and need keys, while a browser is free:

| Need | Try in this order | Why |
|---|---|---|
| Read or act on a website | **Browser** (the user's own signed-in browser) | Free. Does most of what APIs do, with the user's logins. |
| Use a desktop app with no web version | **Computer use** | Only when a browser cannot reach it. |
| Work with the user's own apps (Gmail, Calendar, Drive, Slack, Notion) | **Connector**, only if it is free and easy to connect | Saves the agent from clicking through screens. |
| Anything a browser truly cannot do, or needs high volume or speed | **API and key** | Costs money. Say what it costs and why the browser is not enough. |
| Files and data the agent reads or writes | A folder, a Sheet or a Doc | Name the exact place. |

Check what is already connected in this session (connectors, browser tools) and mark those as ready. For each missing item, say what the user must do (sign in, connect, paste a key) and how long it takes. Never ask the user to paste a secret into the chat. Tell them to set it as an environment variable or in the tool's own settings.

If something the dream needs is unavailable, say so and offer the next-cheapest route. Do not pretend.

## Step 4: Context (taste and background)

Two short questions:

1. **Taste.** "Show me what good looks like." Ask for 1 to 3 references the user loves and, if they have one, 1 they hate: a screenshot, a link, a past email, a draft they wrote, a post, a person's profile. Suggest where to find them (their sent folder, saved posts, a site they admire). If they have none, offer to find 3 candidates in the browser and let them pick. Taste is the part agents cannot guess, and examples to copy beat adjectives.
2. **Background.** Facts about the user, their business and their audience, plus rules (always, never). Pull what you can from their website, bio and memory, then ask them to correct it.

## Step 5: Done when

A good check is **specific, countable and yes or no**, so two strangers would score the same run the same way. This is also what makes the work measurable, and measurable work can be tuned.

Propose 3 to 5 checks and mark them Recommended. Example: "10 companies found, each with a founder profile link", "every message mentions one real detail about the company", "nothing sent without approval."

Also ask two safety questions:
- **What may it do on its own, and what needs a yes first?** Recommend draft-first for anything that sends, posts, pays or deletes, at least for the first 3 runs.
- **When should it stop?** A time limit or count limit, so a bad run cannot go on forever.

## Step 6: Output

The output has to be something the user can use or benefit from right away. Pick the format by asking what the user does next with it:

- **Reads it once:** a message (Telegram, WhatsApp, Slack) or an email at a set time.
- **Keeps it or shares it:** an HTML page (artifact), a PDF or a Doc.
- **Works with it:** a Sheet or a table.
- **Posts or sends it:** a folder of images, videos or drafts, ready to review.

Suggest one main deliverable plus a short summary message, say where and when it arrives, and mark one as Recommended.

Then show the SOP on one screen and ask: "Anything to change?"

```
# SOP: <name>
Task: <what to do, in plain words, with the steps they know work>
Environment: <browser, connectors, files, keys: what is ready, what is missing>
Context: <background, rules, what I know that works, references to copy>
Done when: <3 to 5 yes/no checks, stop rule, what needs approval>
Output: <deliverable, format, where and when it goes>
```

## Step 7: Write the skill first, then run it

Turn the approved SOP into a `SKILL.md` **before** running anything, then run the work by invoking that skill. Reasons: the SOP stays the single source of truth, the first run tests the skill itself (the thing you will tune), and it is versioned from day one. A throwaway prompt cannot be tuned.

The one exception is a clearly one-off job the user will never repeat. Then run it directly and offer the SOP as a prompt.

The skill file contains:
- A pushy `description`: what it does, and the phrases that should trigger it.
- The SOP as the body, with the user's insights in Context.
- A "Done when" checklist the agent grades itself against, with proof for each item.
- A short "Tune log" section for results and changes, and a version comment at the top (`v0.1.0`).
- A rule to stop at anything marked as needing approval.

Keep it under about 200 lines and explain the reason behind each rule instead of shouting MUST. Save it in the user's skills folder if you can write there. If you cannot, show it for review and say where it belongs.

Then ask once: "Run it now?" Recommend yes. When it finishes, show the result **against each Done when check**, passed or failed, with proof. If a check failed, say so plainly and say why.

## Step 8: Tune it daily

This step is the point of the framework. Without it, people build a workflow, forget it, and it rots. Present the setup below as the recommended default and confirm once, because it creates things outside this chat.

1. **Review the first run.** List what passed, what failed, errors, and **anything unexpected** (surprises, new patterns, odd results). Propose **one** change. One change at a time shows what made the difference.
2. **Keep your skills on GitHub.** Recommend one repository for all custom skills (for example `my-skills`), with a folder per skill: `skills/<skill-name>/SKILL.md`, plus a short README and a CHANGELOG. Check whether the user already has one. Default to private. Ask before creating anything. Push the skill, commit with a message that says what changed and why, and tag each version (`<skill-name>-v0.1.0`, then `v0.1.1`). Never commit keys, tokens or personal data.
3. **Set a routine.** A daily run at a time the user picks (suggest 8 PM), using the scheduling tools in this session. If none exist, say so and give the exact steps to schedule it themselves. The routine ends with a short report:

```
Daily report: <skill name> v<version>
Closer to the goal? <yes/no/unclear, with the number>
Done when: <each check, passed or failed>
Errors: <list, or none>
Unexpected: <anything surprising>
Suggested change: <one change, and what it should improve, in a way we can measure>
```

4. **Apply a change** only after the user agrees, bump the version, push it, and run again.

If the user sounds discouraged after a weak first run, tell them that is normal. The agent gets good by being used and tuned every day.

## Rules that protect the user

- Draft, never send, until the user says go. Messages, emails, posts, payments and deletions all need a yes first.
- Never invent results. If a step failed or you could not check something, say that.
- Keep secrets out of chat, files and commits.
- Use the user's own words for their business and goals. Do not rename things they named.
- If the dream could harm someone (spam, scraping private data, impersonation), say so and propose a version that does not.

## When the user wants to move fast

They may say "use recommended" or "you decide". Fill every open item with your Recommended option, show the full SOP with a short list of assumptions, and ask for one overall yes. A full interview should take about 6 questions. Do not add more unless something is truly unclear.

## Worked example

**Dream:** "I wish someone would search the top YC companies, work out which ones need a growth person, and email their founders for me."

- **Specific knowledge:** the YC startup directory lists the companies and links the founders' LinkedIn profiles. YC startups are hiring growth people (a growth hire at a well-known YC company went viral on Twitter). A cold email format the user found that works.
- **Environment:** browser (signed in to LinkedIn and Gmail). No API keys.
- **Context:** the user is a growth marketer. Reference: the cold email they drafted. Rule: one real detail per company.
- **Done when:** 10 companies listed with founder links. 10 drafts, each with one real detail. Nothing sent without a yes.
- **Output:** a Sheet of companies plus drafts, and a 3-line summary on Telegram at 8 AM.
- **Tune:** after each run, one change (for example, a better subject line), pushed as a new version, and an 8 PM report.