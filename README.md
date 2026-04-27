# Writing RSQKit Task Pages with Skills

This guide explains how to use the RSQKit task page Claude skills to draft, refine, and prepare new task pages for submission to the [RSQKit repository](https://github.com/EVERSE-ResearchSoftware/RSQKit).

---

## The Skills

There are four skills in the RSQKit task page family. They are designed to be used in sequence, though some steps are optional depending on your needs.

| Skill | What it does |
|---|---|
| `rsqkit-task-page` | Writes or reviews a task page — structure, voice, content, and Further Reading |
| `rsqkit-task-page-enrich` | Enriches a draft with content from URLs, attachments, or pasted text |
| `rsqkit-task-page-update-tools` | Replaces plain Markdown tool links with `{% tool "id" %}` tags |
| `rsqkit-task-page-metadata` | Generates the YAML front matter block for the top of the page file |

### Recommended workflow

```
1. rsqkit-task-page          — write the draft
2. rsqkit-task-page-enrich   — (optional) deepen with external sources
3. rsqkit-task-page-update-tools  — replace tool links with tool tags
4. rsqkit-task-page-metadata — generate the front matter
```

Steps 2 and 3 can be swapped. Step 4 can happen any time after step 1.

---

## Step-by-Step Guide

### Step 1 — Write the draft

Start a **new conversation** in Claude. Starting fresh keeps the context small and the cost low.

Give Claude a topic and ask it to write a task page. For example:

> "Write an RSQKit task page on how to use software containers for reproducible research."

Claude will use the `rsqkit-task-page` skill to produce a page with:

- An H2 heading framed as a question addressed to the reader
- H3 subheadings: Description, Considerations, Solutions
- Second person voice throughout
- A Further Reading section at the end (H2)
- Plain `[text](url)` Markdown links

If the topic naturally breaks into two or more distinct sub-tasks, Claude will produce multiple H2 blocks, each with its own Description, Considerations, and Solutions.

**Review the draft.** Check that the content is accurate and the balance between sections feels right. Ask Claude to adjust anything that doesn't read well or is missing something important.

---

### Step 2 — Enrich the draft (optional)

If you have useful source material — a URL, an attached document, a paper, or pasted text — ask Claude to enrich the draft:

> "Enrich this draft using the content at [URL]."

or

> "Can you improve this draft using the attached PDF?"

Claude will fetch the URL, read the content, follow any relevant links one level deep, and weave useful material into the draft without changing its structure. It will summarise what changed and why.

This step is particularly useful when:
- A topic has authoritative community guidance you want reflected
- You want to add more specific tool recommendations from a known resource
- The draft feels thin on practical detail

---

### Step 3 — Replace tool links with tool tags

Ask Claude to update the tool links:

> "Update the tool links in this page."

Claude will scan every Markdown link in the page and compare it against the tools registry (`tool_and_resource_list.yml`). Links that match a registered tool are replaced with:

```
{% tool "tool-id" %}
```

Links in the **Further Reading** section are left as plain Markdown links — they are references to books, papers, and documentation, not tool tags.

Claude will also report:
- **What was replaced** — a list of every substitution made
- **What was left as a plain link** — non-tool references (papers, standards, project sites)
- **Potential new tool entries** — links that look like tools but aren't in the registry yet, with suggested YAML entries you can add to `_data/tool_and_resource_list.yml`

If Claude suggests new tool entries, copy the suggested YAML and add it to `_data/tool_and_resource_list.yml` into your RSQKit repository fork (or branch) before submitting your page as a pull request.
---

### Step 4 — Generate the front matter

Ask Claude to generate the page metadata:

> "Can you suggest page metadata for this task page?"

Claude will produce a YAML block ready to paste at the top of your page file, covering:

- `title` — noun-phrase version of the task question
- `description` — 1–2 sentence summary for tile/card views
- `contributors` — leave as `[]` and fill in yourself
- `page_id` — a unique lowercase slug
- `related_pages` — page IDs of related RSQKit task pages
- `quality_indicators` — abbreviations from `quality_indicators.yml`
- `keywords` — lowercase search terms
- `training` — fixed block for the EVERSE TeSS registry

**Review the suggestions carefully**, particularly:

- `related_pages` — check that the page IDs listed actually exist in RSQKit
- `quality_indicators` — check that the indicators listed are genuinely satisfied by following this page's guidance
- `contributors` — add your name (and any co-authors) as it appears in `_data/CONTRIBUTORS.yml`

---

## Assembling the Final Page File

Once you have all four pieces, assemble them in this order:

```
[YAML front matter]
---
[page content]
```

A complete page file looks like this:

```markdown
---
title: "Using software containers for reproducible research"
description: "How to use containers such as Docker and Singularity to create reproducible software environments for research."
contributors: ["Your Name"]
page_id: using_containers
related_pages:
  tasks: [reproducible_software_environments, ci_cd, organising_software_projects]
quality_indicators: [requirements_specified, has_ci-tests]
keywords: ["containers", "docker", "singularity", "reproducibility", "software environments"]
training:
  - name: "EVERSE TeSS"
    url: "https://everse-training.app.cern.ch"
---

## How do you use software containers to make your research software reproducible?

This page provides an overview of containers...

### Description

...

### Considerations

...

### Solutions

...

## Further Reading

...
```

---

## What Goes Where in the RSQKit Repository

Once your page file is ready, here is where each piece belongs in the [RSQKit GitHub repository](https://github.com/EVERSE-ResearchSoftware/RSQKit):

### The task page file

**Location:** `pages/tasks/`

**Filename:** `[page_id].md` — e.g. `using_containers.md`

The file goes in `pages/tasks/` alongside the other task pages. The filename should match the `page_id` in the front matter.

### New tool entries (if any)

**Location:** `_data/tool_and_resource_list.yml`

If the tool update step produced suggested YAML entries for tools not yet in the registry, add them to this file. Each entry follows this format:

```yaml
- id: tool-id
  name: Tool Name
  description: >-
    A short description of what the tool does.
  url: 'https://tool-homepage.example.com/'
  catalog: RSQKit
```

Add new entries at the end of the file. The `catalog` value should be `RSQKit` for tools you are adding as part of RSQKit content work.

### Your contributor entry (if you are new to RSQKit)

**Location:** `_data/CONTRIBUTORS.yml`

If your name is not already listed, add an entry. The minimum required fields are your full name and GitHub username:

```yaml
Your Full Name:
  git: your-github-username
  orcid: 0000-0000-0000-0000   # optional but encouraged
  role: author
  affiliation: Your Institution
```

---

## Submitting to RSQKit

RSQKit uses a standard GitHub pull request workflow.

1. Fork the [RSQKit repository](https://github.com/EVERSE-ResearchSoftware/RSQKit)
2. Create a branch for your new page
3. Add your page file to `pages/tasks/`
4. Add any new tool entries to `_data/tool_and_resource_list.yml`
5. Add your contributor entry to `_data/CONTRIBUTORS.yml` if needed
6. Open a pull request against the `main` branch
7. The RSQKit Editorial Board will review and provide feedback

See the [RSQKit Contribution Guidelines](https://github.com/EVERSE-ResearchSoftware/RSQKit/blob/main/pages/contributing/contribution_guidelines.md) for more detail on the review process.

---

## Tips for Getting the Best Results

**Use a fresh conversation for each page.** The skills work best with a clean context. Long conversations with many files and prior exchanges are more expensive and can produce slightly less consistent output.

**Be specific about the topic.** The more precisely you describe the task, the better the draft. "How do you choose a software licence for research software?" will produce a better result than "software licences".

**Iterate on content before running later skills.** Get the draft right before running the tool update and metadata steps — it avoids having to redo those passes if the content changes significantly.

**Check the Further Reading links.** The skills suggest well-regarded resources, but verify that links are still live, that the resources are still current and that references to sections are accurate before submitting.

**Review quality indicators carefully.** The metadata skill suggests indicators conservatively, but you should confirm each one is genuinely satisfied by a reader following the page's guidance.

---

## Keeping the Skills Up to Date

The `rsqkit-task-page-update-tools` and `rsqkit-task-page-metadata` skills contain embedded reference tables (the tools registry and the quality indicators) that need updating when the underlying data files change.

When `_data/tool_and_resource_list.yml` or `_data/quality_indicators.yml` are updated in the RSQKit repository, provide the updated files to Claude and ask it to update the relevant skill.
