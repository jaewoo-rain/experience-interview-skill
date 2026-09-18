[한국어](./README.md) · **English**

# Experience Interview

A Claude Code skill that **interviews you** to surface real experiences for résumés and cover letters — instead of writing them for you.

It is not a document generator. It asks the questions.

## What's different

Most résumé and cover-letter tools take already-organized experience as input. But being unable to organize it is usually the problem. This skill handles the step before.

Question wording and prohibition rules are drawn from interview and memory research, and **every question carries its source.** The verification status of each piece of evidence (original text checked / secondary source only / could not verify) is stated as well.

### One premise, inverted

Tools like this usually aim to "filter out exaggeration." The evidence says that doesn't work.

- Interviewers detect deception at about **54%** accuracy — a coin flip
- They catch **12–19%** of applicant faking tactics, and 9.6 years of interviewing experience doesn't improve it
- And **probing has been shown to *increase* faking** (Levashina & Campion 2007)

So the goal here is not lie detection. It is **rewriting statements into a form that can be verified in an interview.** A contaminated statement passes the paper screen and collapses in the interview room. Leading questions are banned not as an ethical gesture but as loss avoidance: a narrative the interviewer planted isn't in the candidate's head, so it falls apart the moment someone asks from a different angle.

## How it asks

| Step | What happens | Representative question |
|---|---|---|
| 0 | Remove the evaluation frame, set ground rules | "There are no right or wrong answers" / "If you don't know, say so — don't guess" |
| 1 | Find incidents (no examples given) | "Think of your life as a book. What would you title each chapter?" |
| 2 | Reinstate context | "Picture the room as if you were back there … who was there …(pause) what you could hear" |
| 3 | Separate "I" from "we" | "What **specifically** did you say or do at that moment?" |
| 4 | Surface numbers | "How did you remember it was that many?" → "How sure are you?" |
| 5 | Domain-specific probing | AI/LLM · cloud · backend · data · frontend · robotics · marketing · PM · extracurricular |
| 6 | Meaning and hand-back | "What does this say about you as a person?" / "Did I leave anything out?" |

## What it refuses to do (12 rules, each with evidence)

| Prohibited | Measured effect |
|---|---|
| Presupposing what the person never said | Reported seeing a nonexistent object: **53% vs 35%** |
| Offering number options ("3? 5? 10?") | Mean answer shifted **3.3 → 5.2** — adults, recalling their own past behavior |
| Intensity adverbs ("you did that *frequently*, right?") | **2.2 vs 0.7** times per week |
| Praise and approval ("oh, that's great!") | False allegations **35% vs 12%** — and they persisted after reinforcement stopped |
| Showing examples first | **53%** of reports clustered into the example's category |
| Asking for imagination ("if you had been the lead…") | Imagination inflation — carries risk with no recall benefit |

Full list with citations: `references/금지규칙.md` (Korean).

## Output

Records follow `templates/경험블록.md`. Every episode fills in **situation / problem / my judgment / action / result / what I was thinking and feeling**, and every number carries a four-part set — **denominator, period, measurement tool and environment, definition** — plus a provenance flag: `[measured]` `[estimated]` `[internal]`.

Three things always stay in the record: **role boundary (what I did *not* do)**, **⚠️ needs confirmation**, and **likely interview counter-questions**.

Anything that emerged as "hmm… now that I think about it, I guess so" is tagged `🔁 needs re-confirmation`. Retrieval of a pre-existing memory is accompanied by a feeling of *recognition, not surprise* (Grunert & Grunert 1995).

## No dependencies

No other skills, no MCP servers, no Python scripts, no network calls. Eight Markdown files are the whole thing. Clone it into your skills folder and it works — offline included.

The output can be handed to a résumé or cover-letter skill, but that is optional; the record stands on its own.

## Example

[From "I don't have anything worth writing about" to a record with numbers attached](examples/샘플세션.md) — a full session with a fictional person, the resulting record, and the source technique behind each move. (Korean)

## Install

**Claude Code — available in every project**
```bash
git clone https://github.com/jaewoo-rain/experience-interview-skill.git ~/.claude/skills/experience-interview
```

**One project only**
```bash
git clone https://github.com/jaewoo-rain/experience-interview-skill.git <project>/.claude/skills/experience-interview
```

**Other agents (Codex etc.)**
If the agent supports skill folders, place it under `~/.codex/skills/` the same way. If not, point at `SKILL.md` directly in conversation.

Restart Claude Code after installing and it will appear in the skill list.

## Usage

```
help me organize my experience
I don't think I have anything to write about
this project just wrapped up — record it
is this worth putting on a résumé?
```

Or invoke it directly with `/experience-interview`.

## Files

```
experience-interview/
├── SKILL.md                          flow and principles
├── references/
│   ├── 질문문구.md                    34 staged questions + fallback prompts + ratio rules (sourced)
│   ├── 금지규칙.md                    12 prohibitions with supporting figures
│   ├── 기법과근거.md                  techniques, limits, source list, do-not-cite items
│   ├── 분야별_질문과표현.md            9 domains: probes, overclaim↔safe rewrites, counter-questions
│   └── 세션운영.md                    domain detection, "nothing to write about" path, self-audit, sensitive material
├── templates/경험블록.md              output format
└── examples/샘플세션.md               sample session
```

Contents are in Korean. The method itself is language-independent.

## Grounded in

Cognitive interviewing (Fisher & Geiselman) · Critical Incident Technique (Flanagan 1954) · Behavioral Event Interviews (McClelland, Boyatzis) · Life Story Interview (McAdams) · Laddering (Reynolds & Gutman) · Repertory grid (Kelly) · Cognitive pretesting (Willis) · Motivational interviewing (MITI, SAMHSA TIP 35) · NICHD protocol · UK Ministry of Justice ABE guidance · Leading-question and memory-distortion research (Loftus and others) · Korean competency-based hiring guidebook (HRD Korea) · SFIA and NCS competency frameworks

Sources and access paths are listed in `references/기법과근거.md`, and figures that could not be verified against the original are flagged **do not cite**.

## Limits

- Much of the evidence comes from **forensic interviews and child witnesses.** Effects are likely smaller with adults in a hiring context. That said, the number-anchoring and intensity-adverb experiments (Loftus 1975) had **adults recalling their own past behavior**, so those transfer directly
- **No study applying cognitive interviewing to hiring or HR settings was found**
- All evidence is from English-language research. Whether Korean sentence endings and particles create presupposition the same way English articles do has not been tested
- This skill cannot make memory accurate. **It tries not to contaminate it**

## License

MIT — 양재우 (Jaewoo Yang)

Copyright in the cited research and guidance remains with the respective authors and publishers. This repository summarizes and attributes; it does not redistribute the originals.
