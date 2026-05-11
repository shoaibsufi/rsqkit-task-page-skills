---
# Setting up

- open the file `rsqkit-task-page-skill-as-one-file.md` and copy and paste this into a new chat on Ollama etc
- ask it to produce an RSQKit task page on a topic you are interested in
- You may have to ask it for sections it has missed such as 'Further Reading'
   - e.g. "write me an RSQKit task page draft on building a health community to support your research software"
---

# How do you create an RSQKit task page draft?

## Description
This guide explains how to use the provided RSQKit workflow documentation to draft a new task page. It covers the structure, voice, and tools needed to create a clear, self-contained, and motivating RSQKit task page. Whether you're writing a new page or reviewing an existing one, this guide ensures your content follows RSQKit’s quality principles.

---

## Considerations
- **Purpose**: This guide is for **drafting** task pages. For **enrichment**, **tool updates**, or **metadata generation**, refer to the respective sections in the workflow documentation.
- **Audience**: Researchers, software engineers, and documentation writers who need to create or improve RSQKit task pages.
- **Prerequisites**:
  - Familiarity with Markdown formatting.
  - Access to the provided workflow documentation (this README).
  - A clear topic for your task page (e.g., "How do you write a good README?").
- **Structure**: RSQKit task pages follow a strict format. Deviating from it risks confusing readers or violating RSQKit’s quality principles.
- **Tools**: Use the tools listed in the workflow documentation (e.g., `{% tool "mkdocs" %}` for documentation, `{% tool "github-actions" %}` for automation).
- **Voice**: Always use **second-person voice** ("you," "your") to address the reader directly. Avoid third-person or casual language.
- **Links**: All links must use **standard Markdown format** (`[text](URL)`). Never use raw URLs or nested links.

---

## Solutions

### Step 1: Choose Your Topic
Before drafting, define the **specific task** your page will address. Use a clear, direct question as your heading (e.g., "How do you write a good README?").
- **Example**: "How do you use static analysis to improve research software quality?"
- **Avoid vague topics**: "Research software quality" is too broad. Instead, focus on a specific action or sub-task.

---

### Step 2: Draft the Task Page Structure
Use the **core RSQKit structure** for each task or sub-task. Every block follows this hierarchy:
```
## How do you [task question]?        ← H2: Task question (no "Task" heading)
### Description                        ← H3: What the task is and why it matters
### Considerations                     ← H3: Key points to think about
### Solutions                          ← H3: How to do the task
```

#### Example Draft for "How do you write a good README?"
```markdown
## How do you write a good README for your research software?

### Description
*(Write 2–4 sentences explaining the task and its importance. Use second-person voice.)*
*A well-written README helps users understand your software’s purpose, setup, and usage. It’s essential for research software to ensure clarity and maintainability. This page provides guidance on structuring, writing, and maintaining a README that effectively communicates your software’s value.*

### Considerations
*(List 3–5 bulleted points addressing trade-offs, audience needs, or key insights. Use second-person where natural.)*
- **Audience**: Tailor the README to your target users (e.g., researchers, developers).
- **Structure**: Follow a clear hierarchy (e.g., title, description, installation).
- **Accessibility**: Use plain language and visual aids where helpful.
- **Updates**: Keep the README current with the latest version of your software.

### Solutions
*(Provide actionable steps or conceptual guidance. Link to high-quality external resources rather than duplicating content.)*
- **Structure the README**:
  - Start with a **clear title** and **short description**.
  - Include sections for installation, usage, configuration, contributing, and license.
- **Write for clarity**:
  - Use **second-person voice** ("You install the package with `pip install`").
  - Include **code blocks** for commands or snippets.
```

---

### Step 3: Write the Description Section
The **Description** section should:
- Explain **what the task is** and **why it matters** to the reader.
- Be **scoped to the specific task** (not the wider topic).
- Use **2–4 sentences** and avoid padding.

#### Example:
```markdown
### Description
*A well-written README helps users understand your software’s purpose, setup, and usage. It’s essential for research software to ensure clarity and maintainability. This page provides guidance on structuring, writing, and maintaining a README that effectively communicates your software’s value.*
```

---

### Step 4: Populate the Considerations Section
The **Considerations** section should include:
- **Trade-offs**, **audience insights**, or **key points** the reader should keep in mind.
- A **bulleted list** for brevity and scannability.
- **Second-person voice** where natural (e.g., "You should consider...").

#### Example:
```markdown
### Considerations
- **Audience**: Tailor the README to your target users (e.g., researchers, developers).
- **Structure**: Follow a clear hierarchy (e.g., title, description, installation).
- **Accessibility**: Use plain language and visual aids where helpful.
- **Updates**: Keep the README current with the latest version of your software.
```

---

### Step 5: Provide Solutions
The **Solutions** section should include:
- **Actionable steps** or **conceptual guidance** for completing the task.
- **Distinguish between guidance and steps** where appropriate.
- **Link to high-quality external resources** rather than duplicating content.

#### Example:
```markdown
### Solutions
- **Structure the README**:
  - Start with a **clear title** and **short description**.
  - Include sections for installation, usage, configuration, contributing, and license.
- **Write for clarity**:
  - Use **second-person voice** ("You install the package with `pip install`").
  - Include **code blocks** for commands or snippets.
- **Automate updates**:
  - Use `{% tool "github-actions" %}` to auto-generate READMEs from code metadata.
```

---

### Step 6: Add a Further Reading Section
Every RSQKit task page must end with a **Further Reading** section. This section:
- Lists **3–5 authoritative and highly regarded external resources**.
- Orders **practical/tool-focused resources first**, followed by **theoretical resources**.
- Includes a **2–3 sentence description** for each entry explaining its value.

#### Example:
```markdown
## Further Reading
- **[Google’s Style Guide for Documentation](https://google.github.io/styleguide/docguide/#s-README)** — A comprehensive guide to writing clear, concise documentation. This resource is particularly useful for structuring your README to be accessible to a broad audience, including non-technical researchers.
- **[MkDocs Documentation](https://www.mkdocs.org/)** — A static site generator for project documentation, ideal for projects with complex READMEs or multi-page documentation needs.
- **[FAIR Data Management Principles for Software](https://www.go-fair.org/fair-principles/)** — The FAIR principles (Findable, Accessible, Interoperable, Reusable) are critical for research software documentation.
```

---

### Step 7: Add an AI Disclosure Section
Every RSQKit task page must end with an **AI Disclosure** section. This section:
- Contains a **single fixed line of text** with `<model>` replaced by the actual model name used to produce the page.
- Must be placed **immediately after Further Reading**.

#### Example:
```markdown
## AI Disclosure
This work was produced with the assistance of Claude Sonnet 4.6, under the strict editorial control and factual verification of the human author.
```

---

## Writing and Review Checklist
Use this checklist to ensure your draft meets RSQKit’s quality principles:

### Structure
- [ ] Page uses the correct heading hierarchy: H2 for task question(s), H3 for Description/Considerations/Solutions.
- [ ] The word "Task" does not appear as a heading.
- [ ] Sub-tasks each have their own full block.
- [ ] No headings are missing or at the wrong level.
- [ ] Page ends with `## Further Reading` (H2).
- [ ] Page ends with `## AI Disclosure` (H2) after Further Reading.

### Voice
- [ ] Task heading (H2) is addressed directly to the reader in second person.
- [ ] Description speaks to the reader ("when you are working on...").
- [ ] Considerations bullets use second person where natural.
- [ ] Solutions steps address the reader directly ("choose a tool", "start with...").
- [ ] Tone is professional and direct throughout.

### Task Heading (H2)
- [ ] The H2 heading is the task question itself, not the word "Task".
- [ ] The scope is specific (not vague like "Research software quality").
- [ ] Optional one-sentence body text beneath the heading states what the page provides.

### Description Section
- [ ] Explains what the problem/task is and why it matters to the reader.
- [ ] Scoped to this task, not the wider topic.
- [ ] 2–4 sentences; no padding.

### Considerations Section
- [ ] Lists things the reader genuinely needs to keep in mind.
- [ ] Includes relevant trade-offs, characteristics, key insights.
- [ ] No filler bullets; each point earns its place.

### Solutions Section
- [ ] Actionable and/or conceptually useful.
- [ ] Distinguishes guidance from steps where appropriate.
- [ ] Links to high-quality external resources rather than reproducing their content.
- [ ] Does not leave the reader with nothing actionable.

### Further Reading Section
- [ ] Contains 3–5 entries; no more, no fewer unless quality demands it.
- [ ] Practical/tool-focused resources appear before theoretical/book resources.
- [ ] Each entry has a description explaining why it is worth reading and what value it offers.
- [ ] All resources are freely accessible online where possible.
- [ ] No padding — every entry is there for a reason.

### Overall Quality
- [ ] Reader can form a correct understanding without following any links.
- [ ] Links present are to high-quality, stable, relevant external material.
- [ ] Content is factually accurate and reflects current good practice.
- [ ] No unnecessary duplication of content that external resources handle better.
- [ ] Tone is direct and practical — not academic, not marketing.

---

## Common Failure Modes to Avoid
- **Malformed links**: Always use `[Link text](URL)` and nothing else. No backticks inside link text, no nested links, no raw URLs as link text.
- **"Task" used as a heading**: The word "Task" should never appear as a heading; the task question itself is the H2 heading.
- **Wrong heading levels**: Task questions are H2, Description/Considerations/Solutions are H3, Further Reading is H2.
- **Vague task framing**: "Software testing" is not a task. "How do you decide which tests to write for your research software?" is.
- **Third person voice**: Writing "researchers should..." or "teams need to..." instead of addressing the reader directly as "you".
- **Second person that feels casual**: "You" does not mean informal; maintain professional register throughout.
- **Description that doesn't explain why it matters**: Don't just describe the topic; say why it's important for the reader's research software quality.
- **Considerations that are obvious**: Cut bullets like "Testing takes time" unless they lead somewhere useful.
- **Solutions that are only links**: External links are good but the reader must get something actionable even without clicking.
- **Solutions that reproduce external content at length**: Summarise, frame, and link; don't copy.
- **Missing sub-task blocks**: If the topic has distinct sub-tasks, each needs its own full block.
- **Conflating guidance and steps**: Be clear about what is conceptual versus what is an action to take.
- **Missing Further Reading section**: Every page needs one; don't omit it.
- **Missing AI Disclosure section**: Every page needs one immediately after Further Reading; don't omit it.
- **Wrong model name in AI Disclosure**: Use the actual model active in the current conversation, not a placeholder or a guess.

---

## Next Steps
After drafting your RSQKit task page:
1. **Enrich the draft** with external sources using the `rsqkit-task-page-enrich` skill.
2. **Update tool links** with tool tags using the `rsqkit-task-page-update-tools` skill.
3. **Generate metadata** for the page using the `rsqkit-task-page-metadata` skill.

For more details on these steps, refer to the respective sections in the RSQKit workflow documentation.

---
