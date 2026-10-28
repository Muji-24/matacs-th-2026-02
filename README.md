# AI Proposal Triage Design

**Candidate:** Mujtaba Rehman  
**Reference:** MATACS-TH-2026-02  
**Time spent:** ~60 minutes  

## Repository Contents

| File | Description |
|---|---|
| [WRITEUP.md](WRITEUP.md) | Answers to the five design questions (process design, consistency, human oversight, changing criteria, risks) |
| [PROMPTS.md](PROMPTS.md) | AI prompts for structured extraction and qualitative scoring, ready to use |
| [ranking.json](ranking.json) | Expected ranking of proposals A–E with scores and reasoning |
| [diagram/process-flow.png](diagram/process-flow.png) | Process-flow diagram from upload to ranked output |
| [prototype/](prototype/) | Working Python script that calls the Gemini API for real AI extraction and scoring |

## AI Tool Usage

I used Claude to help structure my writeup and draft the AI prompts. I also used it to scaffold the prototype script. I reviewed and edited all outputs for example, Claude's initial extraction prompt did not include an explicit injection-detection field (`injection_flag`), and its scoring rubric for the "experience" criterion used vague qualitative bands instead of concrete install-count thresholds. I rewrote both to be more specific and auditable.
