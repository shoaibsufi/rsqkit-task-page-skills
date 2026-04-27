---
name: rsqkit-task-page
description: Use this skill whenever the user wants to write, draft, improve, review, or quality-assure an RSQKit task page. Trigger when the user mentions RSQKit, asks to write or review a task page, asks for help with a task-description-considerations-solutions structure, or is working on content about research software quality. Also trigger when the user says things like "help me write a page about X for RSQKit", "can you review this task page?", "draft the considerations section for this RSQKit task", "does this follow the RSQKit format?", or any similar phrasing. Always use this skill when working on RSQKit content.
---
 
# RSQKit Task Page Skill
 
RSQKit task pages are structured guidance pages that help researchers and research software engineers understand and act on research software quality topics. Each page must be accurate, self-contained enough to be useful on its own, and motivate readers to learn more.
 
---
 
## Core Principles
 
Every RSQKit task page must satisfy these quality criteria:
 
1. **Clarity of purpose** — The reader must immediately understand why the topic matters and why this task is important for research software quality.
2. **Accuracy** — Content must be factually correct and reflect current good practices in research software.
3. **Self-sufficiency** — If external links are not followed, the page still gives the correct impression and enough guidance to apply the information correctly.
4. **Appropriate depth** — Provide a conceptual overview and practical guidance. If a topic is well-covered by high-quality external material, point to it rather than duplicating it.
5. **Motivation to learn more** — Link out to high-quality external documentation, standards, training materials, or community guidance.
6. **Correct overall impression** — A reader leaving the page without following any links should have an accurate mental model of the task and how to approach it.
---
 
## Voice and Tone
 
All RSQKit task pages are written in the **second person** ("you", "your"). Address the reader directly throughout — in the Task heading, the Description, the Considerations bullets, and the Solutions steps. This is the established convention for RSQKit pages.
 
Examples:
- ✓ "How do you use static analysis to improve the quality of your research software?"
- ✗ "How to use static analysis to improve research software quality"
- ✓ "When you are working on research software where correctness is critical..."
- ✗ "For research software where correctness is critical..."
- ✓ "You and your team should agree on which rules to enable."
- ✗ "Teams should agree on which rules to enable."
Maintain a professional, direct tone throughout. Second person should not make the writing feel informal — it should feel like a knowledgeable colleague speaking directly and practically to the reader.
 
---
 
## Link Formatting
 
**All links must use simple standard Markdown link syntax — no exceptions:**
 
```
[Link text](URL)
```
 
Link text should be descriptive and human-readable: a tool name, a document title, or a short phrase. Never use backticks inside link text, and never nest a link inside another link.
 
- ✓ `[ruff](https://docs.astral.sh/ruff/)`
- ✓ `[Ruff documentation](https://docs.astral.sh/ruff/)`
- ✓ `[pre-commit](https://pre-commit.com/)`
- ✗ backtick-wrapped text inside a link: the backticks belong outside or not at all
- ✗ a link nested inside another link: one URL, one label, one pair of brackets
This rule applies everywhere on the page — Solutions bullets, Considerations, Further Reading entries, and body text. Never expose raw URLs as link text; always use a human-readable label.
 
---
 
## Page Format
 
RSQKit task pages use a repeating structure. Each distinct task or sub-task gets its own block of four headings. If the overall page topic breaks into distinct sub-tasks, repeat the full block for each one. Every page also ends with a **Further Reading** section.
 
### Block structure
 
The heading hierarchy is as follows:
 
```
## How do you [task question]?        ← H2: the task or sub-task question itself
### Description                        ← H3
### Considerations                     ← H3
### Solutions                          ← H3
```
 
For a page with two sub-tasks, the structure would be:
 
```
## How do you [first sub-task question]?
### Description
### Considerations
### Solutions
 
## How do you [second sub-task question]?
### Description
### Considerations
### Solutions
 
## Further Reading
```
 
#### Task heading (H2)
- The task or sub-task question is the H2 heading itself — do not use "Task" as the heading word.
- Frame it as a clear, specific question addressed directly to the reader (e.g. *"## How do you write a good README for your research software?"*).
- Optionally, add one sentence of body text beneath the heading briefly stating what the page aims to provide (e.g. overview, practical guidance, and pointers to further resources). Keep this tight — one sentence at most.
#### Description (H3)
- A short, direct explanation of what the task or problem is about and why it matters to the reader.
- This is not an introduction to the wider topic — it's scoped to this specific task.
- Aim for 2–4 sentences. Avoid padding.
#### Considerations (H3)
- The things the reader should keep in mind when thinking about this task: benefits, trade-offs, choices, key insights, characteristics of good or bad solutions.
- A bulleted list is preferred for brevity and scannability.
- Write bullets in second person where natural ("Your existing codebase may have..."), but don't force it where it reads awkwardly.
- Each bullet should add value — cut anything self-evident or generic.
#### Solutions (H3)
- The steps and approaches for actually undertaking the task, informed by the considerations.
- A bulleted list is preferred.
- Where helpful, distinguish between **conceptual guidance** (what to think about) and **actionable steps** (what to do).
- Where high-quality external resources exist, link to them here rather than reproducing their content at length.
### Further Reading section
 
Further Reading is an H2 heading (`## Further Reading`), sitting at the same level as the task heading(s). Every page ends with it. This is a curated list of 3–5 authoritative and highly regarded external resources — tools, documentation, books, papers, or guides — that a reader can follow to go deeper on the topic.
 
**Ordering:** list practical and tool-focused resources first (documentation, guides, frameworks), then broader or more theoretical resources (papers, books) at the end.
 
**Format for each entry:**
```
- **[Title](URL)** — A 2–3 sentence description explaining what the resource is, why it is authoritative or highly regarded, and specifically what value it offers to someone who has just read this page. Where relevant, note what type of reader will benefit most.
```
 
**Key principles for Further Reading:**
- Prefer resources that are freely accessible online where possible.
- Each entry must earn its place — it should offer something distinct from the others.
- Do not include resources just to pad the list; 3 strong entries are better than 5 weak ones.
- The description should explain *why* the resource is worth reading, not just *what* it is.
- Avoid resources that are behind paywalls unless they are genuinely the best available source on the topic.
### AI Disclosure section
 
Every page ends with an **AI Disclosure** section immediately after Further Reading. It is an H2 heading (`## AI Disclosure`).
 
The section contains a single fixed line of text, with `<model>` replaced by the actual Claude model name used to produce the page:
 
```
This work was produced with the assistance of Claude <model>, under the strict editorial control and factual verification of the human author.
```
 
**How to determine the model name:** use the model currently active in the conversation. Examples:
 
- Claude Sonnet 4.6 → `Claude Sonnet 4.6`
- Claude Opus 4.6 → `Claude Opus 4.6`
- Claude Haiku 4.5 → `Claude Haiku 4.5`
If you are uncertain which model is active, ask the user to confirm before generating this section.
 
The full page ending therefore looks like:
 
```
## Further Reading
 
- ...
 
## AI Disclosure
 
This work was produced with the assistance of Claude Sonnet 4.6, under the strict editorial control and factual verification of the human author.
```
 
---
 
## Writing and Review Checklist
 
Use this checklist when drafting or reviewing a task page.
 
### Structure
- [ ] Page uses the correct heading hierarchy: H2 for task question(s), H3 for Description / Considerations / Solutions.
- [ ] The word "Task" does not appear as a heading — the task question itself is the H2 heading.
- [ ] Sub-tasks each have their own full H2 block (not crammed into one block).
- [ ] No headings are missing or at the wrong level.
- [ ] Page ends with `## Further Reading` (H2).
- [ ] Page ends with `## AI Disclosure` (H2) after Further Reading.
- [ ] AI Disclosure text uses the correct model name for the current conversation.
### Voice
- [ ] Task heading (H2) is addressed directly to the reader in second person.
- [ ] Description speaks to the reader ("when you are working on...").
- [ ] Considerations bullets use second person where natural.
- [ ] Solutions steps address the reader directly ("choose a tool", "start with...").
- [ ] Tone is professional and direct throughout — second person does not mean casual.
### Task heading (H2)
- [ ] The H2 heading is the task question itself, not the word "Task".
- [ ] The scope is specific (not vague like "Research software quality").
- [ ] Optional one-sentence body text beneath the heading states what the page provides, if needed.
### Description section
- [ ] Explains what the problem/task is and why it matters to the reader.
- [ ] Scoped to this task, not the wider topic.
- [ ] 2–4 sentences; no padding.
### Considerations section
- [ ] Lists things the reader genuinely needs to keep in mind.
- [ ] Includes relevant trade-offs, characteristics, key insights.
- [ ] No filler bullets; each point earns its place.
### Solutions section
- [ ] Actionable and/or conceptually useful.
- [ ] Distinguishes guidance from steps where appropriate.
- [ ] Links to high-quality external resources rather than reproducing their content.
- [ ] Does not leave the reader with nothing actionable.
### Further Reading section
- [ ] Contains 3–5 entries; no more, no fewer unless quality demands it.
- [ ] Practical/tool-focused resources appear before theoretical/book resources.
- [ ] Each entry has a description explaining why it is worth reading and what value it offers.
- [ ] All resources are freely accessible online where possible.
- [ ] No padding — every entry is there for a reason.
### Overall quality
- [ ] Reader can form a correct understanding without following any links.
- [ ] Links present are to high-quality, stable, relevant external material.
- [ ] Content is factually accurate and reflects current good practice.
- [ ] No unnecessary duplication of content that external resources handle better.
- [ ] Tone is direct and practical — not academic, not marketing.
---
 
## Common Failure Modes to Avoid
 
- **Malformed links** — always use `[Link text](URL)` and nothing else. No backticks inside link text, no nested links, no raw URLs as link text.
- **"Task" used as a heading** — the word "Task" should never appear as a heading; the task question itself is the H2 heading.
- **Wrong heading levels** — task questions are H2, Description/Considerations/Solutions are H3, Further Reading is H2. Do not flatten everything to H2 or nest incorrectly.
- **Vague task framing** — "Software testing" is not a task. "How do you decide which tests to write for your research software?" is.
- **Third person voice** — writing "researchers should..." or "teams need to..." instead of addressing the reader directly as "you".
- **Second person that feels casual** — "you" does not mean informal; maintain professional register throughout.
- **Description that doesn't explain why it matters** — don't just describe the topic; say why it's important for the reader's research software quality.
- **Considerations that are obvious** — cut bullets like "Testing takes time" unless they lead somewhere useful.
- **Solutions that are only links** — external links are good but the reader must get something actionable even without clicking.
- **Solutions that reproduce external content at length** — summarise, frame, and link; don't copy.
- **Missing sub-task blocks** — if the topic has distinct sub-tasks, each needs its own full block.
- **Conflating guidance and steps** — be clear about what is conceptual versus what is an action to take.
- **Missing Further Reading section** — every page needs one; don't omit it.
- **Missing AI Disclosure section** — every page needs one immediately after Further Reading; don't omit it.
- **Wrong model name in AI Disclosure** — use the actual model active in the current conversation, not a placeholder or a guess.
- **Further Reading that just describes resources without explaining their value** — each entry must say why it is worth reading, not just what it is.
- **Further Reading ordered theory-first** — practical and tool-focused resources come before books and papers.
---
 
## Notes on Additional Passes
 
RSQKit task pages may require additional passes after initial drafting, depending on context. These include:
 
- **Page metadata** (frontmatter, tags, category, etc.) — handled separately.
- **Internal links** (cross-references to other RSQKit pages) — handled separately.
- **External resource vetting** (checking link quality, currency, and longevity, including Further Reading entries) — may be handled by a separate skill.
- **Enrichment** (adding content from provided URLs, attachments, or text) — handled by the `rsqkit-task-page-enrich` skill.
When writing or reviewing, focus on structure, voice, and content quality. Flag where links or metadata will be needed, but do not block on them.
