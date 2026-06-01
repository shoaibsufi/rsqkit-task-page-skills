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
