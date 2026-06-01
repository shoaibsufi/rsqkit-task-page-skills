**This is experimental *only* - the master version of Research Software Story interviewer is here - https://github.com/sparkslabs/EVERSE-Seminar-Nov2025-ResearchSoftwareStories/tree/main/GPT-PromptTools**

# RSQKit Research Software Story Interviewer

A Claude skill that runs a guided interview to help someone produce a complete [RSQKit Research Software Story](ihttps://everse.software/RSQKit/research_software_storieshttps://everse.software/RSQKit/) — a structured narrative describing a research software project. Claude asks the questions, tracks what is known and what is missing, and generates a publication-ready draft that fills in the RSQKit Research Software Story template.

## What it does

The skill turns a blank template into a finished story through a conversation. Rather than handing someone a form to fill in, Claude conducts a warm, plain-spoken interview — one question at a time — ingesting any existing material first, probing where answers are thin, and only then writing a draft. It never invents facts: anything unconfirmed is flagged as a TODO rather than guessed.

The output matches the RSQKit template structure exactly, in British English, ready to open as a pull request.

## How to use it

1. **Install the skill** `rsqkit-story-interviewer.skill` in an environment where Claude can load skills. It will then trigger automatically on phrases like "help me write a research software story", "interview me about my software for RSQKit", or "fill in the research software story template".

2. **Start the conversation.** Claude opens by asking whether you have any existing material — a README, a paper, notes, or a previous write-up. Provide whatever you have; it shortens the interview considerably. If you have nothing, the interview starts from scratch.

3. **Answer the questions.** Claude works through eleven sections in a fixed order (Problem → User Community → Technical Aspects → Libraries and Systems → Software Practices → Developer Community → Tools → FAIR & Open → Documentation → Sustainability → References). It asks one question at a time and follows up only where needed. Before leaving each section it asks "what am I missing?", and it marks each section as Content, TODO, Deferred, or N/A.

4. **Generate the draft.** When you say "Generate Draft 0", Claude produces the full story as continuous prose (with the FAIR & Open section as bullets), fills in the YAML front matter, and collects every outstanding TODO in a labelled block at the end. It can also add optional appendices: Lessons, Impact, and Future Directions.

5. **Iterate.** After the draft you can ask Claude to revise a section, write an executive summary, generate fact-check prompts for a reviewer, or remind you of the export steps (adding yourself to `_data/CONTRIBUTORS.yml` and listing the page in `_data/sidebars/main.yml`).

## File structure

```
rsqkit-story-interviewer/
├── SKILL.md
└── references/
    ├── template.md
    ├── question_script.md
    └── deep_probes.md
```

### `SKILL.md`

The main skill file and the only one Claude reads at the start. It defines the interviewer's voice and behaviour, the four-phase process (Ingestion → Interview → Draft → Review), the canonical section order, the rules for generating Draft 0, and the anti-hallucination constraints. It points to the three reference files and tells Claude when to read each one, so the larger reference content is only loaded when it is actually needed.

### `references/template.md`

The RSQKit Research Software Story template itself — the document the whole process exists to fill in. Claude reads this at draft-generation time so the output matches the official structure exactly, including the YAML front matter fields and the section headings. Keeping it as a reference file means the skill stays aligned automatically if the template is updated from upstream.

### `references/question_script.md`

The Level 1 (core) questions, organised by section. These are the primary questions Claude asks during the interview — the backbone of the conversation. Claude reads this file during the interview phase and asks the questions one at a time, in order.

### `references/deep_probes.md`

The optional follow-up questions, organised by the same sections. Claude reads these during the interview and uses them only when a core answer is thin, ambiguous, or clearly incomplete — drawing out detail without overwhelming the interviewee with a long list of questions up front. They are the depth layer beneath the question script.

## Design notes

- **Two distinct community sections.** Section 2 (User Community) is about who *uses* the software — disciplines, institutions, experience levels. Section 6 (Developer Community) is about who *contributes* — how development is organised, onboarding resources, mentorship, governance. These are deliberately kept separate in both the interview and the draft.
- **No invented content.** Users, metrics, dependencies, licences, and dates are only written into the draft when confirmed. Everything else is a TODO.
- **British English** throughout, matching RSQKit house style.

## Use with other than Claude

A system prompt is available in `standalone/rsqkit-research-software-story-interviewer-system-prompt.md`, copy and paste this into any LLM and then it should behave in the same way as the Claude skill, however sometimes you have to nudge it to move you to the next section depending on the LLM system used.
`
