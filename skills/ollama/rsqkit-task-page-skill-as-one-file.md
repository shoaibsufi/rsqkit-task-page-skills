### Workflow: Create a draft RSQKit task page
**Input:** [What is the topic of the page?]
**Steps:**

**rsqkit-task-page (Draft)**
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

**rsqkit-task-page-enrich (Optional)**
---
name: rsqkit-task-page-enrich
description: Use this skill whenever the user wants to enrich an RSQKit task page draft with additional content from external sources — text, file attachments, web pages, or links found on those pages. Trigger when the user says things like "enrich this task page", "add content from this link", "pull in information from this attachment", "can you improve this draft using these resources?", "use this page to improve the task page", or similar. Also trigger when the user provides URLs, files, or pasted text and asks for them to be incorporated into an existing RSQKit draft. Always use this skill as an enrichment pass after rsqkit-task-page has produced a draft, or when enriching an existing task page.
---
 
# RSQKit Task Page Enrichment Skill
 
This skill performs an enrichment pass on an existing RSQKit task page draft. It takes external material — pasted text, file attachments, and/or web pages — fetches and reads that material, follows links found on those pages (one level deep only), and uses the gathered content to improve the draft.
 
The output is still a valid RSQKit task page. The enrichment pass does not change the format — it improves the content within it.
 
---
 
## What Enrichment Does
 
Enrichment improves the draft by:
 
- **Adding factual depth** — inserting accurate details, nuance, or context from the source material that the draft lacks.
- **Improving the Considerations section** — surfacing trade-offs, audience insights, or key points from the sources that belong there.
- **Strengthening the Solutions section** — adding actionable steps, tools, or approaches found in the sources; linking to high-quality external resources rather than reproducing them at length.
- **Replacing vague guidance with specific guidance** — if the draft says something generic that a source says more precisely, prefer the precise version.
- **Adding or improving links** — where a source is high-quality and stable, add it as a link in the appropriate section.
Enrichment does **not**:
- Change the Task → Description → Considerations → Solutions structure.
- Add content that isn't supported by the sources or existing good knowledge.
- Reproduce substantial content from external sources verbatim — summarise, frame, and link.
- Follow links from pages that the fetched pages themselves link to (one level deep only).
---
 
## Enrichment Process
 
### Step 1 — Establish the baseline draft
 
Identify the current RSQKit task page draft. This may be:
- The output of the most recent `rsqkit-task-page` skill run in this conversation.
- A draft pasted in by the user.
- A draft in an attached file.
If no draft is clearly identifiable, ask the user to provide or confirm it before proceeding.
 
### Step 2 — Gather source material
 
Collect all provided sources:
 
**Pasted text** — Use as-is. Note the origin if the user has described it.
 
**File attachments** — Read any attached files (PDFs, docs, markdown, etc.). Extract relevant content.
 
**Web pages (URLs)** — Fetch each URL provided by the user using the web fetch tool. Read the full page content.
 
**One level of links** — From each fetched web page, identify links that look relevant to the task page topic. Fetch those linked pages too. Do not follow links from those second-level pages — stop there.
 
> **Link relevance filter**: Only follow links that are plausibly relevant to the task page topic. Skip navigational links, unrelated content, login pages, and anything that looks like it won't add value. Use judgement — the goal is depth on the topic, not exhaustive crawling.
 
### Step 3 — Extract relevant content
 
From all gathered material, identify:
 
- Facts, definitions, or explanations that add depth to the Description.
- Insights, trade-offs, audience considerations, or key points for the Considerations section.
- Actionable steps, tools, methods, or approaches for the Solutions section.
- High-quality resources worth linking to directly.
Discard:
- Content that duplicates what the draft already says well.
- Content that is off-topic, outdated, or of low quality.
- Content that would only make sense reproduced verbatim (summarise instead, or link).
### Step 4 — Integrate into the draft
 
Rewrite the draft sections where enrichment adds value. For each change:
 
- Prefer precision over length — a tighter, more accurate sentence beats a longer one.
- Add links in the Solutions section (or Considerations where appropriate) using the format: `[Link text](URL)`.
- Do not pad sections just because source material exists — only add what genuinely improves the page.
- Maintain the RSQKit quality principles: the page must still be self-sufficient, accurate, and motivating.
### Step 5 — Output
 
Produce the enriched task page in full, using the standard RSQKit format. 
 
Optionally, provide a brief summary of what was changed and why — useful when the user wants to understand what the enrichment pass did.
 
---
 
## Quality Check After Enrichment
 
After integrating sources, verify the page still meets the RSQKit core principles:
 
- [ ] Reader can still form a correct understanding without following any links.
- [ ] No section has become bloated with content better left to external resources.
- [ ] All added links point to high-quality, relevant, stable external material.
- [ ] Content is factually accurate — sources have been interpreted correctly.
- [ ] The Task → Description → Considerations → Solutions structure is intact.
- [ ] Added content doesn't contradict existing good content in the draft.
---
 
## Scope Boundaries
 
| In scope | Out of scope |
|---|---|
| Pasted text provided by the user | Content from links on pages linked by the fetched pages (2+ levels deep) |
| Attached files (PDF, doc, md, etc.) | Fabricating content not in the sources |
| URLs provided by the user | Changing the RSQKit page format |
| Links found on fetched pages (1 level deep, relevant only) | Reproducing external content verbatim at length |
 
---
 
## Notes
 
- This skill is designed to run **after** `rsqkit-task-page` has produced a draft, but can also enrich an existing published task page.
- Additional passes for **page metadata**, **internal cross-links**, and **resource vetting** are out of scope here and handled separately.
- If no source material meaningfully improves the draft, say so rather than making superficial changes.
   - Task: Deepen the draft with external sources (e.g., Wikipedia, official docs, or citations).
   - Example: "Add references to Python’s `requests` documentation and a real-world use case."
   - *Skip this step if not needed.*


**rsqkit-task-page-update-tools**
---
name: rsqkit-task-page-update-tools
description: Use this skill whenever the user wants to replace tool links in an RSQKit task page with the RSQKit tool tag syntax {% tool "id" %}. Trigger when the user says things like "update the tool links", "replace links with tool tags", "add tool tags to this page", "convert links to tool syntax", or any similar phrasing. Also trigger when the user wants to check whether tools mentioned on a page exist in the tool_and_resource_list.yml file, or wants suggestions for new tool entries to add to that file. Always use this skill after rsqkit-task-page has produced a draft and before rsqkit-task-page-metadata is run, though order relative to rsqkit-task-page-enrich is flexible.
---
 
# RSQKit Task Page Update Tools Skill
 
This skill scans an RSQKit task page for links to tools and replaces them with the RSQKit tool tag syntax. It also identifies tool links that are not yet in the tools registry and suggests YAML entries for them.
 
---
 
## What This Skill Does
 
1. **Scans** the task page for all Markdown links: `[text](url)`
2. **Matches** each link against the tools registry (by URL, name, or description)
3. **Replaces** matched links with `{% tool "id" %}`
4. **Identifies** unmatched links and decides whether they are tools needing registry entries, or non-tool references (documents, papers, project sites, standards) that should be left as plain links
5. **Outputs** the updated page and, where applicable, suggested YAML entries for new tools
---
 
## Tool Tag Syntax
 
The replacement format is:
 
```
{% tool "id" %}
```
 
where `id` is the `id` field from `tool_and_resource_list.yml`. The tag replaces the entire Markdown link — both the link text and the URL.
 
**Example:**
 
```
Before: [ruff](https://docs.astral.sh/ruff/)
After:  {% tool "ruff" %}
 
Before: [Ruff documentation](https://docs.astral.sh/ruff/)
After:  {% tool "ruff" %}
 
Before: [pre-commit](https://pre-commit.com/)
After:  {% tool "precommit" %}
```
 
Note that the tool tag replaces the link entirely — the link text is discarded because the tag renders with the tool's name from the registry.
 
---
 
## Matching Rules
 
### URL matching
Compare the link URL against the `url` field in the registry. Apply these normalisation rules before comparing:
- Strip a trailing `/` from both URLs before comparing (treat `https://example.com/` and `https://example.com` as identical)
- Treat `http://` and `https://` as equivalent
- Ignore case differences in the domain
### Name matching
If URL matching fails, compare the link text against the `name` field in the registry (case-insensitive). This catches cases where a tool is linked with a slightly different URL but an identical or near-identical display name.
 
### Description matching
If both URL and name matching fail, check whether the link text or URL strongly suggests a tool that exists in the registry (e.g. a known alias, abbreviation, or variant spelling). Use judgement conservatively — only match on description if confident.
 
### Precedence
URL match > name match > description match. If uncertain, do not match — flag it as unmatched instead.
 
---
 
## Classifying Unmatched Links
 
Not every link is a tool. When a link has no registry match, classify it as one of:
 
**Leave as a plain link (not a tool):**
- Academic papers or preprints (arXiv, DOI links, journal URLs)
- Standards documents (e.g. W3C, ISO, IETF specs)
- Project or initiative homepages that are not software tools (e.g. a research project website, a community initiative)
- Documentation pages that describe a concept rather than a tool (e.g. a Wikipedia article, a language spec page)
- Registry or repository entries for a specific software package (e.g. a Zenodo record, a PyPI package page for a specific library)
**Flag as a potential new tool entry:**
- A link to a tool's homepage, documentation site, or GitHub repository where the linked thing is clearly software that researchers or developers would use directly
- A link where the display text is a tool name and the URL goes to that tool's official site or repo
When in doubt, err toward leaving the link as-is rather than incorrectly tagging it.
 
---
 
## Process
 
### Step 1 — Identify the page and the registry
Establish the task page to process. The tools registry is embedded in this skill (see **Tools Registry** section below). If the user provides an updated `tool_and_resource_list.yml`, use that instead and note that the embedded registry may be out of date.
 
### Step 2 — Extract all links
Find every Markdown link in the page: `[text](url)`. Note the link text, the URL, and its location in the page.
 
### Step 3 — Match against registry
For each link, attempt URL match, then name match, then description match. Record the result: matched (with registry id) or unmatched.
 
### Step 4 — Classify unmatched links
For each unmatched link, decide: leave as plain link, or flag as potential new tool.
 
### Step 5 — Apply replacements
Rewrite the page, replacing matched links with `{% tool "id" %}`. Leave all other links unchanged.
 
### Step 6 — Output
 
Produce three outputs:
 
**A) The updated page** — the full task page with tool tags substituted.
 
**B) A summary of replacements made**, in this format:
```
Replaced:
- [ruff](https://docs.astral.sh/ruff/) → {% tool "ruff" %}
- [pre-commit](https://pre-commit.com/) → {% tool "precommit" %}
 
Left as plain links (not tools):
- [Software Engineering at Google](https://abseil.io/resources/swe-book) — book/reference
- [Continuous Delivery](https://continuousdelivery.com/) — book/reference
 
Potential new tool entries (not in registry):
- [clang-tidy](https://clang.llvm.org/extra/clang-tidy/) — C++ linter, likely a tool
- [cppcheck](https://cppcheck.sourceforge.io/) — C++ static analysis, likely a tool
```
 
**C) Suggested YAML entries** for any links flagged as potential new tools, in the format used by `tool_and_resource_list.yml`:
 
```yaml
- id: clang-tidy
  name: clang-tidy
  description: >-
    clang-tidy is a clang-based C++ linter tool that provides an extensible
    framework for diagnosing and fixing typical programming errors, style
    violations, and interface misuse.
  url: 'https://clang.llvm.org/extra/clang-tidy/'
  catalog: RSQKit
```
 
Generate the description from what you know about the tool. Flag it clearly as a suggested entry that the user should review before adding to the file.
 
---
 
## Important Constraints
 
- **Do not modify Further Reading links.** The Further Reading section contains links to books, papers, and documentation resources. These should always remain as plain Markdown links — do not replace them with tool tags even if a tool in the registry has the same URL or name. Further Reading is for human-readable references, not tool tags.
- **Do not modify internal RSQKit page links** (relative links or links to other RSQKit pages).
- **Preserve link context.** When a tool is mentioned multiple times on the page, replace all occurrences.
- **Do not add tool tags for tools not in the registry** — only suggest YAML entries; never emit `{% tool "id" %}` for an id that does not exist in the registry.
---
 
## Tools Registry
 
The following is the embedded tools registry extracted from `tool_and_resource_list.yml`. This may become outdated as the file changes. If the user provides an updated file, use that instead.
 
| id | name | url |
|---|---|---|
| `mypy` | mypy | https://mypy-lang.org/ |
| `spdx` | SPDX | https://spdx.org/licenses/ |
| `choosealicense` | Choose an open source license | https://choosealicense.com/ |
| `bash` | Bash | https://www.gnu.org/software/bash/ |
| `powershell` | PowerShell | https://learn.microsoft.com/en-gb/powershell/ |
| `opencl` | OpenCL | https://www.khronos.org/opencl/ |
| `cuda` | CUDA | https://developer.nvidia.com/cuda-zone |
| `rust` | Rust | https://www.rust-lang.org/ |
| `julia` | Julia | https://julialang.org/ |
| `r` | R | https://www.r-project.org/ |
| `typescript` | TypeScript | https://www.typescriptlang.org/ |
| `javascript` | JavaScript | https://developer.mozilla.org/en-US/docs/Web/JavaScript |
| `cpp` | C++ | https://isocpp.org/ |
| `python` | Python | https://www.python.org/ |
| `java` | Java | https://www.java.com/en/ |
| `docker` | Docker | https://www.docker.com/ |
| `docker-compose` | Docker Compose | https://docs.docker.com/compose/ |
| `howfairis` | howfairis | https://github.com/fair-software/howfairis |
| `github` | GitHub | https://github.com/ |
| `zenodo` | Zenodo | https://zenodo.org/ |
| `figshare` | FigShare | https://figshare.com/ |
| `vscode` | Visual Studio Code | https://code.visualstudio.com/ |
| `intellij-idea` | IntelliJ IDEA | https://www.jetbrains.com/fr-fr/idea/ |
| `poetry` | Poetry | https://python-poetry.org/ |
| `pypi` | Python Package Index (PyPi) | https://pypi.org/ |
| `eossr` | eOSSR | https://gitlab.com/escape-ossr/eossr |
| `chatgpt` | ChatGPT | https://chatgpt.com/ |
| `javadoc` | JavaDoc | https://www.oracle.com/java/technologies/javase/javadoc-tool.html |
| `hugo` | Hugo | https://gohugo.io/ |
| `pelican` | Pelican | https://getpelican.com/ |
| `gitlab-pages` | GitLab Pages | https://docs.gitlab.com/ee/user/project/pages/ |
| `github-pages` | GitHub Pages | https://pages.github.com/ |
| `github-actions` | GitHub Actions | https://github.com/features/actions |
| `gitlab-ci-cd` | GitLab CI/CD | https://docs.gitlab.com/ee/topics/build_your_application.html |
| `bandit` | Bandit | https://github.com/PyCQA/bandit |
| `playwrite` | Playwrite | https://playwright.dev/docs/intro |
| `scorep` | Score-P | https://gitlab.com/score-p/scorep |
| `fuji` | F-UJI | https://github.com/softwaresaved/fuji/ |
| `bearer` | Bearer | https://github.com/bearer/bearer |
| `hermesworkflows` | Hermes Workflows | https://docs.software-metadata.pub/en/latest/ |
| `cffinitgenerator` | CFFINIT Generator | https://citation-file-format.github.io/cff-initializer-javascript/#/ |
| `codemetagenerator` | CodeMeta Generator | https://codemeta.github.io/codemeta-generator |
| `codemeta` | CodeMeta | https://codemeta.github.io/ |
| `sqaaas` | SQAaas | https://sqaaas.eosc-synergy.eu/ |
| `gitleaks` | gitleaks | https://github.com/gitleaks/gitleaks |
| `black` | Black | https://github.com/psf/black |
| `precommit` | precommit | https://pre-commit.com/ |
| `reuse` | REUSE | https://reuse.software/ |
| `fairaware` | FAIR Aware | https://fairaware.dans.knaw.nl/ |
| `creativecommons-licence-chooser` | Creative Commons License Chooser | https://chooser-beta.creativecommons.org/ |
| `mkdocs` | MKDocs | https://www.mkdocs.org/ |
| `pytest` | Pytest | https://docs.pytest.org/en/latest/ |
| `testthat` | testthat | https://testthat.r-lib.org/ |
| `test-jl` | Test.jl | https://docs.julialang.org/en/v1/stdlib/Test/ |
| `tox` | tox | https://tox.wiki/en/4.23.2/ |
| `junit` | JUnit | https://junit.org/junit5/ |
| `cppunit` | CPPUnit | https://freedesktop.org/wiki/Software/cppunit/ |
| `apptainer` | Apptainer | https://apptainer.org/ |
| `singularity` | Singularity | https://sylabs.io/singularity/ |
| `packer` | Packer | https://www.packer.io/ |
| `ruff` | Ruff | https://docs.astral.sh/ruff/ |
| `pylint` | Pylint | https://pylint.readthedocs.io/en/stable/ |
| `hadolint` | Hadolint | https://github.com/hadolint/hadolint |
| `flake8` | Flake8 | https://flake8.pycqa.org/en/latest/ |
| `checkstyle` | Checkstyle | https://catalogforge.net/projects/checkstyle/ |
| `gcov` | Gcov | https://gcc.gnu.org/onlinedocs/gcc/Gcov.html |
| `valgrind` | Valgrind | https://valgrind.org/ |
| `dvc` | DVC | https://dvc.org/ |
| `dependabot` | Dependabot | https://github.com/dependabot/dependabot-core |
| `sonarqube` | SonarQube | https://www.sonarcatalog.com/products/sonarqube/ |
| `selenium` | Selenium | https://pypi.org/project/selenium/ |
| `jupyterbook` | Jupyter-Book | https://pypi.org/project/jupyter-book/ |
| `git` | Git | https://git-scm.com/ |
| `jenkins` | Jenkins | https://www.jenkins.io/ |
| `travis` | Travis | https://www.travis-ci.com/ |
| `kubernetes` | Kubernetes | https://kubernetes.io/ |
| `cmake` | CMake | https://cmake.org/ |
| `nixos` | NixOS | https://nixos.org/ |
| `guix` | Guix | https://guix.gnu.org/ |
| `rpm` | RPM | https://rpm.org/ |
| `zammad` | Zammad | https://zammad.com/en |
| `inveniordm` | InvenioRDM | https://inveniosoftware.org/products/rdm/ |
| `softwareheritage` | Software Heritage | https://www.softwareheritage.org |
| `jasonldvalidator` | JSON-LD validator | https://json-ld.org/playground |
| `somef` | SOMEF | https://github.com/KnowledgeCaptureAndDiscovery/somef |
| `somefvider` | SOMEF Vider | https://somef.linkeddata.es/ |
| `readthedocs` | Read the Docs | https://about.readthedocs.com/ |
| `sphinx` | Sphinx | https://www.sphinx-doc.org |
| `gitlab` | GitLab | https://about.gitlab.com/ |
| `greenalgorithms` | Green Algorithms | https://www.green-algorithms.org/ |
| `codecarbon` | CodeCarbon | https://codecarbon.io/ |
| `greenspectorstudio` | Greenspector Studio | https://greenspector.com/en/home/ |
| `carbontracker` | carbontracker | https://github.com/lfwa/carbontracker |
| `ecograder` | Ecograder | https://ecograder.com/ |
| `pep8` | PEP8 | https://peps.python.org/pep-0008/ |
| `r-language-style-guide` | R Style Guide | https://google.github.io/styleguide/Rguide.html |
| `code-linters` | Code Linters | https://en.wikipedia.org/wiki/Lint_%28software%29 |
| `google-programming-style-guide` | Google's programming style guide | https://google.github.io/styleguide/ |
| `pycharm` | PyCharm | https://www.jetbrains.com/pycharm/ |
| `eclipse` | Eclipse | https://eclipseide.org/ |
| `jsdoc` | JSDoc | https://jsdoc.app/ |
| `python-docstring-generator` | Python Docstring Generator | https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring |
| `doxygen` | Doxygen | https://www.doxygen.nl/ |
| `swagger` | Swagger | https://swagger.io/ |
| `roxygen` | Roxygen | https://roxygen2.r-lib.org/ |
| `mercurial` | Mercurial | https://www.mercurial-scm.org/ |
| `subversion` | Subversion | https://github.com/apache/subversion |
| `perforce` | Perforce | https://www.perforce.com/ |
| `git-lfs` | Git Large File Storage | https://git-lfs.github.com/ |
| `rstudio` | RStudio | https://posit.co/download/rstudio-desktop/ |
| `pip` | pip | https://pypi.org/project/pip/ |
| `uv` | uv | https://github.com/astral-sh/uv |
| `venv` | venv | https://docs.python.org/3/library/venv.html |
| `renv` | renv | https://rstudio.github.io/renv/index.html |
| `conda` | Conda | https://anaconda.org/anaconda/conda |
| `semantic-versioning` | Semantic Versioning | https://semver.org/ |
| `calendar-versioning` | Calendar Versioning | https://calver.org/ |
| `pkg-jl` | Pkg.jl | https://pkgdocs.julialang.org/v1/ |
| `conan` | Conan | https://conan.io/ |
| `maven` | Maven | https://maven.apache.org/ |
| `bundler` | Bundler | https://bundler.io/ |
| `fair-python-coockiecutter` | FAIR Python Coockiecutter | https://github.com/Materials-Data-Science-and-Informatics/fair-python-cookiecutter |
| `documenter-jl` | Documenter.jl | https://documenter.juliadocs.org/stable/ |
| `prettier-code-formatter` | Prettier | https://prettier.io/ |
| `fortran` | Fortran | https://fortran-lang.org/ |
| `vagrant` | Vagrant | https://www.vagrantup.com/ |
| `ansible` | Ansible | https://docs.ansible.com/ansible/latest/getting_started/index.html |
| `terraform` | Terraform | https://www.terraform.io/ |
| `wdl` | Workflow Description Language | https://openwdl.org/ |
| `galaxy` | Galaxy | https://galaxyproject.org/ |
| `keras` | Keras | https://github.com/keras-team/keras |
| `tortellini-action` | tortellini-action | https://github.com/marketplace/actions/tortellini-action |
| `somesy` | Somesy | https://github.com/Materials-Data-Science-and-Informatics/somesy |
| `claude` | Claude | https://claude.ai/new |
| `github-copilot` | Github Copilot | https://github.com/features/copilot |
| `jupyter-book` | Jupyter Book | https://pypi.org/project/jupyter-book/ |
| `scanoss` | SCANOSS | https://www.scanoss.com/ |
| `nextflow` | Nextflow | https://www.nextflow.io |
| `snakemake` | Snakemake | https://snakemake.readthedocs.io |
| `parsl` | Parsl | https://parsl.readthedocs.io/en/stable/userguide/workflows/workflow.html |
| `apache-airflow` | Apache Airflow | https://airflow.apache.org/ |
| `lifemonitor` | LifeMonitor | https://lifemonitor.eu |
| `workflowhub` | WorkflowHub | https://workflowhub.eu/ |
| `reprozip` | ReproZip | https://www.reprozip.org/ |
| `bitbucket` | BitBucket | https://bitbucket.org/ |
| `dockstore` | Dockstore | https://dockstore.org/ |
| `eslint` | ESLint | https://eslint.org/ |
| `angular` | Angular | https://angular.io/ |
| `nestjs` | NestJS | https://nestjs.com/ |
| `jest` | Jest | https://jestjs.io/ |
| `nodejs` | Node.js | https://nodejs.org/ |
| `mongodb` | MongoDB | https://www.mongodb.com/ |
| `mongoose` | Mongoose | https://mongoosejs.com/ |
| `orcid` | ORCID | https://orcid.org/ |
| `bip-scholar` | BIP! Scholar | https://bip.imsi.athenarc.gr/scholar |
| `nginx` | Nginx | https://nginx.org/ |
| `apache-http-server` | Apache HTTP Server | https://httpd.apache.org/ |
| `domereg` | DOME Registry | https://registry.dome-ml.org |
| `osaieco` | OSAI AI Ecosystem | https://osai.dome-ml.org/ai-ecosystem |
| `software-management-wizard` | Software Management Wizard | https://smw.dsw.elixir-europe.org/ |
| `autocodemeta` | Auto CodeMeta generator | https://autocodemeta.linkeddata.es/ |
| `flowr` | flowR | https://github.com/flowr-analysis/flowr |
| `pixi` | Pixi | https://pixi.prefix.dev/latest/ |
| `nanobind` | nanobind | https://nanobind.readthedocs.io/en/latest/ |
| `ctest` | ctest | https://cmake.org/cmake/help/latest/manual/ctest.1.html |
| `cargo` | cargo | https://doc.rust-lang.org/cargo/ |
| `maqao` | maqao | https://maqao.org/ |
| `malt` | malt | https://memtt.github.io/malt/doc/latest/ |
| `renovate` | renovate | https://docs.renovatebot.com/ |
| `cran` | CRAN | https://cran.r-project.org/ |
| `biotools` | bio.tools | https://bio.tools/ |
| `fair-rs-evaluator` | FAIRsoft Evaluator | https://openebench.bsc.es/observatory/Evaluation |
| `fair-rs-checklist` | FAIR software checklist | https://fairsoftwarechecklist.net |
| `codecheck` | CODECHECK | https://codecheck.org.uk/ |
| `pyright` | Pyright | https://github.com/microsoft/pyright |
| `lintr` | lintr | https://lintr.r-lib.org/ |
| `clang-tidy` | clang-tidy | https://clang.llvm.org/extra/clang-tidy/ |
| `cppcheck` | cppcheck | https://cppcheck.sourceforge.io/ |
| `fortran-linter` | fortran-linter | https://github.com/cphyc/fortran-linter |
| `flint` | flint | https://github.com/JonasToth/flint |
| `jet-jl` | JET.jl | https://aviatesk.github.io/JET.jl/stable/ |
| `aqua-jl` | Aqua.jl | https://juliatesting.github.io/Aqua.jl/stable/ |
 
*Note: this registry is embedded from `tool_and_resource_list.yml` at the time this skill was last updated. If the user provides an updated version of the file, use that in preference to this table. When the file is updated, this skill should be updated too.*


**rsqkit-task-page-metadata**
---
name: rsqkit-task-page-metadata
description: Use this skill whenever the user wants to generate, suggest, review, or improve the YAML front matter metadata for an RSQKit task page. Trigger when the user asks to "add metadata", "generate the front matter", "suggest page metadata", "what should the metadata be?", "write the YAML header", or any similar phrasing. Also trigger when the user has a drafted or existing RSQKit task page and wants to make it publication-ready with correct metadata. Always use this skill when working on RSQKit page metadata, even if the user just says "can you add the metadata to this page?".
---
 
# RSQKit Task Page Metadata Skill
 
This skill generates and reviews the YAML front matter metadata block for RSQKit task pages. Metadata appears at the very top of a page file, delimited by `---` before and after it.
 
---
 
## Metadata Format
 
A complete task page metadata block looks like this:
 
```yaml
---
title: "Page title here"
description: "Short description of what this page covers, used in tile/card views."
contributors: ["Full Name One", "Full Name Two"]
page_id: page_id_slug
related_pages:
  tasks: [page_id_one, page_id_two]
quality_indicators: [indicator_abbreviation_one, indicator_abbreviation_two]
keywords: ["keyword one", "keyword two", "keyword three"]
training:
  - name: "EVERSE TeSS"
    url: "https://everse-training.app.cern.ch"
---
```
 
---
 
## Field-by-Field Guidance
 
### `title`
The full display title of the page. Used as the H1 heading in the rendered page. Should match the main Task heading of the page content closely, but as a noun phrase rather than a question.
- ✓ `"Using static analysis"`
- ✗ `"How do you use static analysis?"`
### `description`
A short, plain-prose description of what this page covers. This appears in tile/card views when pages are listed (e.g. search results, related pages). Aim for 1–2 sentences. Write in third person, not second person.
- ✓ `"How to use AI tools to assess the quality of your research software."`
- ✗ `"You should read this if you want to know about AI quality tools."`
### `contributors`
A list of contributors who authored or contributed significantly to the page. Each name must match an entry in the RSQKit `_data/CONTRIBUTORS.yml` file. If you do not know who contributed, leave this as an empty list `[]` and flag it for the user to complete.
 
### `page_id`
A unique slug identifier for this page. Used in `related_pages` references on other pages.
- Use lowercase letters and underscores only — no hyphens, no spaces.
- Base it on the most meaningful part of the page title.
- Examples: `static_analysis`, `ai_quality_assessment`, `creating_good_readme`, `licensing_software`
- Check existing page IDs (listed below) to avoid conflicts.
### `related_pages`
A list of `page_id`s of other RSQKit task pages that are related to this one. These appear as "Related pages" on the rendered page. The format is:
 
```yaml
related_pages:
  tasks: [page_id_one, page_id_two]
```
 
**How to select related pages**: choose pages that a reader of this page would plausibly also benefit from reading — either because the topic is a prerequisite, a natural next step, or closely overlapping. Do not list everything; be selective. A list of 2–5 is typical.
 
See the **Existing Page IDs** section below for all current page IDs you can reference.
 
### `quality_indicators`
A list of quality indicator abbreviations from the RSQKit `quality_indicators.yml` file. These are the indicators most directly relevant to the topic of the page — i.e., indicators that a reader applying this page's guidance would be helping to satisfy.
 
Leave as `[]` if no indicators clearly apply.
 
See the **Quality Indicators Reference** section below for all current abbreviations and descriptions.
 
### `keywords`
A list of lowercase keyword strings related to the topic. Used to power search within RSQKit and to connect to external training registries (e.g. TeSS). 
 
Guidelines:
- Reuse keywords already used on related pages where appropriate — this helps build a consistent folksonomy across RSQKit.
- Include the core topic term(s), common synonyms, and any tool names or standards that are central to the page.
- Aim for 3–8 keywords. Avoid padding with generic terms like "software" or "research" unless they are genuinely distinctive.
- All lowercase.
### `training`
This section is fixed and should be copied verbatim for every task page. It connects the page to the EVERSE TeSS training registry using the page's keywords.
 
```yaml
training:
  - name: "EVERSE TeSS"
    url: "https://everse-training.app.cern.ch"
```
 
Do not modify this block. If the training registry configuration changes in future, update this skill accordingly.
 
---
 
## Existing Page IDs
 
Use these when populating `related_pages`. These are all current RSQKit task pages:
 
| page_id | Title |
|---|---|
| `archiving_software` | Archiving software |
| `ci_cd` | Continuous Integration and Continuous Delivery/Deployment |
| `citing_software` | Citing software |
| `code_review` | Performing a code review |
| `complete_bibliographic_metadata_codemeta` | Creating bibliographic metadata with CodeMeta |
| `computational_workflows` | Computational workflows |
| `creating_good_readme` | Creating a good README |
| `documenting_code` | Documenting code |
| `documenting_software_project` | Documenting software project |
| `documenting_software_readthedocs` | Documenting software using 'Read The Docs' |
| `fair_rs` | Adopting FAIR research software practices |
| `improving_environmental_sustainability` | Improving environmental sustainability |
| `languages_tools_infrastructures` | Choosing languages, tools & infrastructures |
| `licensing_software` | Licensing software |
| `organising_software_projects` | Organising software projects |
| `packaging_software` | Packaging software |
| `publishing_software` | Publishing software |
| `releasing_software` | Releasing software |
| `reproducible_software_environments` | Reproducible software environments |
 
*Note: this list reflects the task pages as of the time this skill was last updated. New pages may have been added since. Ask the user to confirm if you are unsure whether a related page exists.*
 
---
 
## Quality Indicators Reference
 
Use abbreviations from this list when populating `quality_indicators`. Only include indicators that are directly relevant to the task the page is about — indicators that a reader applying the page's guidance would be helping to satisfy.
 
| Abbreviation | Name | Description (summary) |
|---|---|---|
| `archived_in_scholarly_repository` | Software is archived in a scholarly repository | Source code is archived in a scholarly repository (e.g. Zenodo, HAL) |
| `archived_in_software_heritage` | Software is archived in Software Heritage | Source code is found in the Software Heritage universal archive |
| `codemeta_completeness` | CodeMeta completeness | The codemeta.json file is sufficiently complete per community expectations |
| `coupling_between_objects_ok` | Coupling between objects follows community conventions | CBO ratio is at a reasonable level per community standards |
| `cyclomatic_complexity_ok` | Cyclomatic complexity follows community conventions | Cyclomatic complexity follows community-established conventions |
| `dependency_management` | Software has dependency management solution | External libraries and dependencies are managed for compatibility and security |
| `descriptive_metadata` | Software has descriptive metadata | Software comes with descriptive metadata (name, language, keywords, dates, etc.) |
| `functional_correctness` | Has a measure of functional correctness | A quantifiable measure of functional/computational correctness is reported |
| `has_ci-tests` | Software has continuous integration tests | The project runs tests before pull requests are merged |
| `has_contribution_guidelines` | Software repository has contribution guidelines | The repository provides contribution guidelines for contributors |
| `has_no_linting_issues` | Software has no linting issues | The project addresses warnings from compilers, safe modes, or linters |
| `has_published_package` | Software is published as a downloadable package | The software is published as a downloadable package |
| `has_releases` | Software has releases | The software has tagged releases in its repository |
| `human_code_review_requirement` | Software requires human code review | The project requires human code review before pull requests are merged |
| `internal_cohesion_ok` | Cohesion among methods/functions follows community conventions | Module cohesion is at a reasonable level per community expectations |
| `lines_of_code_ok` | Number of lines of code follows community standards | Lines of code per component follow community conventions |
| `listed_in_registry` | Software is listed in a registry | The source code is listed in a disciplinary or community registry |
| `metadata_is_up_to_date` | Software has up-to-date metadata | Metadata reflects the current, accurate description of the software |
| `no_critical_vulnerability` | No critical vulnerabilities | Reported critical vulnerabilities have been fixed |
| `no_leaked_credentials` | No leaked credentials | No hardcoded secrets, passwords, or API keys are stored in the repository |
| `persistent_and_unique_identifier` | Software has persistent and unique identifier | The software has a persistent, resolvable identifier (e.g. DOI, SWHID) |
| `repository_workflows` | Software has CI/CD workflows in its repository | The project uses workflows to automate testing and deployment |
| `requirements_specified` | Software specifies requirements | The project specifies what is required to use the software |
| `software_has_citation` | Software uses citation | The project uses a citation file (e.g. CITATION.cff) or similar |
| `software_has_documentation` | Software has documentation | The project comes with documentation (README, ReadTheDocs, etc.) |
| `software_has_license` | Software has license | The project has a published license |
| `software_has_tests` | Software provides tests | The software includes unit, integration, or system tests |
| `software_test_coverage` | Software has sufficient test coverage | The test suite covers most code branches, inputs, and functionality |
| `static_analysis_common_vulnerabilities` | Has static analysis for common vulnerabilities | At least one static analysis tool is used to detect common vulnerabilities |
| `support_issue_tracking` | Software provides issue tracking | The project has an accessible issue tracking system |
| `uses_fuzzing` | Software uses fuzzing | The project uses fuzzing or dynamic analysis for memory safety |
| `uses_tool_for_warnings_and_mistakes` | Software uses a tool for warnings or mistakes | The project uses a linter, compiler warning flags, or safe language mode |
| `version_control_use` | Software makes use of version control | The software uses version control |
| `versioning_standards_use` | Software follows versioning standards | Versions follow an established convention (SemVer, CalVer, etc.) |
 
*Note: the quality_indicators.yml file changes over time. If the user provides an updated version of the file, update this skill's reference table accordingly.*
 
---
 
## Process for Generating Metadata
 
When asked to generate metadata for a task page:
 
1. **Read the page content** — understand the topic, the task(s) covered, and the tools or practices discussed.
2. **Derive `title`** — use a noun-phrase version of the main Task heading.
3. **Write `description`** — one or two sentences summarising what the page covers, in third person.
4. **Set `contributors`** — ask the user if not clear from context; do not invent names.
5. **Generate `page_id`** — lowercase slug from the most meaningful part of the title. Check against the existing page IDs list to avoid conflicts.
6. **Select `related_pages`** — scan the existing page IDs list and select 2–5 pages that are genuinely related. Reason briefly about why each is included if it is not obvious.
7. **Select `quality_indicators`** — scan the indicators reference table and select those that the page's guidance directly helps to satisfy. Be conservative — a short accurate list is better than a long speculative one.
8. **Choose `keywords`** — include the core topic term(s), tool names or standards covered, and any synonyms likely to be used in search. Check keywords used on related pages and reuse where appropriate.
9. **Copy `training` block** verbatim.
10. **Output the complete metadata block**, delimited by `---`, ready to be placed at the top of the page file.
---
 
## Common Mistakes to Avoid
 
- **Inventing page IDs** — only reference page IDs from the existing page IDs list; do not guess.
- **Over-populating quality_indicators** — only include indicators the page's content directly helps satisfy, not every vaguely related one.
- **Title as a question** — the `title` field should be a noun phrase, not the second-person question used in the Task heading.
- **description in second person** — the `description` field is used in tile views and should be in third person, unlike the page body.
- **Missing training block** — every task page needs the training block; do not omit it.
- **Modifying the training block** — copy it verbatim; do not change the name or URL.
- **Keywords with capital letters** — all keywords should be lowercase.


---
**Your Input:**

