# Deep Probes — Follow-Up Questions

Use these only when a Level 1 answer is thin, ambiguous, or clearly incomplete.
Ask one probe at a time. Stop probing when you have enough to write the section.

---

## The Problem

- How did people do this before the software existed?
- Why was that painful or inadequate?
- What becomes possible now that wasn't before?
- What assumptions sit behind the problem — what does the software take for granted?
- What is out of scope — what does the software deliberately not try to solve?

---

## User Community

- How broad is the user base — a handful of specialists, a whole experiment or community, or something wider?
- Who relies on the software indirectly — for example, downstream tools or workflows that depend on it?
- Are there users who stretch the software in ways the developers didn't originally anticipate?
- Are there gaps in the user base — people who should be using it but aren't yet?

---

## Technical Aspects

- How is the codebase organised under the hood — is it modular, monolithic, something else?
- What data does it work with, and how large or complex can that data get?
- Where are the performance bottlenecks or hardest technical constraints?
- When did development start, and roughly how active is it now?

---

## Libraries and Systems

- Which dependencies are the most critical — what would break if they changed?
- Are there version constraints, platform constraints, or compatibility requirements worth noting?
- What does someone need to know before contributing to the codebase?

---

## Software Practices

- How do you know the software is working correctly — is anything automated?
- Could someone else reproduce your results from scratch using what exists?
- Is there anything informal but important that isn't written down anywhere?

---

## Developer Community

- Is there a single point of failure — one person without whom development would stall?
- How are decisions made about what gets built or merged?
- What does a new contributor typically do first, and where do they usually get stuck?
- What is the first meaningful contribution someone can make relatively quickly?
- Are there workshops, training events, or mentorship schemes for new contributors?
- Are there example projects, notebooks, or guided exercises that help people learn the codebase?

---

## Tools

- What is automated — are there CI/CD pipelines, linters, formatters, pre-commit hooks?
- How is the software packaged or distributed?
- How do you debug it when something goes wrong?

---

## FAIR and Open

- Where exactly would someone go to discover the software — a registry, a repository, a website?
- What does someone need in order to access and run it?
- Can parts of the software be reused independently, or does it only make sense as a whole?
- What licence is it under?

---

## Documentation

- What forms of documentation exist — README, API docs, tutorials, a wiki, notebooks?
- Who maintains the documentation, and is it kept in sync with the software?
- What do you wish existed that currently doesn't?

---

## Sustainability

- Will this software realistically exist in three to five years?
- What funding supports development or maintenance, and what happens when it ends?
- What risks — technical, organisational, or financial — could stop the project?

---

## References

- Are there similar tools — and what makes this one different?
- Are there relevant papers, either about the software itself or the research it supports?
- Are there standards or specifications the software implements or aligns with?
