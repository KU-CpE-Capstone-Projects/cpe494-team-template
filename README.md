# TeamXX — [Project title]

> CpE-494 / CpE-495 Capstone · Department of Computer Engineering · Kuwait University · **Original plan** (weekly briefs B1–B16)
> Replace every `TeamXX`, `[Insert ...]` and `___` in this file in your team's first pull request.

## Team

| Name | Student ID | Role | GitHub username |
| --- | --- | --- | --- |
| [Insert name] | [Insert ID] | Team leader | @___ |
| [Insert name] | [Insert ID] | ___ | @___ |
| [Insert name] | [Insert ID] | ___ | @___ |
| [Insert name] | [Insert ID] | ___ | @___ |

**Supervisor(s):** [Insert names] · **TA / engineer:** [Insert name]
**Teams channel:** [Insert link] · **Project board:** [Insert link]

## One-line summary

[Insert: who has the problem, what the system does, in one sentence. No brand names.]

## Deliverables

Each official submission goes on Moodle **and** gets a release tag in this repo at the same commit (see [Tagging a submission](#tagging-a-submission)). Update the Status and Tag columns when you submit.

### CpE-494 (Fall)

| # | Milestone | Briefs | Week | Folder | Status | Release tag |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Team formation (team leader selection, team contract) | — | 1 | `docs/494/01-team-formation` | Not started | `494-team-formation-v1.0` |
| 2 | Concept poster + SWOT, proposal presentation | B1, B2 | 2 | `docs/494/02-proposal` | Not started | `494-proposal-v1.0` |
| 3 | Project abstract (interviews started) | B3 | 5 | `docs/494/03-abstract` | Not started | `494-abstract-v1.0` |
| 4 | Requirements chapter (survey, ethical analysis, use cases) + literature review | B4, B5, B6 | 8 | `docs/494/04-requirements-ch1` | Not started | `494-req-ch1-v1.0` |
| 5 | PoC specification + UML and non-UML diagrams | B7, B8, B9 | 10 | `docs/494/05-poc-and-diagrams` | Not started | `494-poc-spec-v1.0` |
| 6 | Detailed design (Chapter 5) + Decision Records | B10, B13 | 12 | `docs/494/06-detailed-design` | Not started | `494-design-v1.0` |
| 7 | Recorded PoC demo, Q&A prep, backup slides; design committee (week 14) | B11, B12 | 13–14 | `docs/494/07-poc-demo-and-committee` | Not started | `494-committee-v1.0` |
| 8 | Project portfolio | — | 14 | `docs/494/08-portfolio` | Not started | `494-portfolio-v1.0` |

### CpE-495 (Spring)

| # | Milestone | Briefs | Week | Folder | Status | Release tag |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Close committee feedback: scope lock, KPIs, Decision Records | B13 | 3 | `docs/495/01-close-committee-feedback` | Not started | `495-feedback-closed-v1.0` |
| 2 | Progress meetings and status reports | — | ongoing | `docs/495/02-progress-meetings` | Not started | `495-progress-1`, `-2`, … |
| 3 | Integrated prototype | — | 9 | `docs/495/03-integrated-prototype` | Not started | `495-prototype-v1.0` |
| 4 | Test plan (Chapter 3) | B14 | 11 | `docs/495/04-test-plan` | Not started | `495-test-plan-v1.0` |
| 5 | Usability testing | B15 | 12 | `docs/495/05-usability-testing` | Not started | `495-usability-v1.0` |
| 6 | Final report | B16 | 14 | `docs/495/06-final-report` | Not started | `495-final-report-v1.0` |
| 7 | Final presentation draft; final committee (week 16) | B16 | 15–16 | `docs/495/07-final-presentation-and-committee` | Not started | `495-final-committee` |
| 8 | Project poster | — | 16 | `docs/495/08-poster` | Not started | `495-poster-v1.0` |
| 9 | Project portfolio | — | 16 | `docs/495/09-portfolio` | Not started | `495-portfolio-v1.0` |

Weeks follow the supervisor's original-plan calendar (week 1 = first teaching week). Edit the Week column if your posted dates differ. Brief codes match the task posts in your Teams class channel.

## Repository map

| Folder | What goes there |
| --- | --- |
| `docs/494`, `docs/495` | One folder per milestone, in order. Final PDF + editable source (`.docx`). See `docs/README.md` for where each brief's work goes. |
| `docs/494/presentations`, `docs/495/presentations` | Slide decks (`.pptx` + exported `.pdf`). |
| `docs/diagrams` | Diagram sources (draw.io, PlantUML, Visio) and exported PNG/SVG. |
| `meetings` | Weekly meeting minutes, one file per meeting: `YYYY-MM-DD.md`. |
| `decisions` | Decision Records (DR-01, DR-02, ...): every major design choice and why. |
| `research` | Interview guides, survey instruments, **anonymized** results. No names, phone numbers or raw recordings. |
| `hardware` | Bill of materials, circuit diagrams, datasheets you rely on. |
| `src` | All code and firmware. |
| `tests` | Test scripts, test data and test logs that back the Chapter 3 results. |

## How we work

1. **Every piece of work starts as an issue** (Task, User story or Bug), tagged with the brief it answers (B1–B16). No issue, no work.
2. **Branch per issue**: `feature/12-camera-capture`, `docs/7-chapter1-needs`, `fix/31-gps-timeout`.
3. **Pull request into `main`**, linked to the issue (`Closes #12`). At least one teammate reviews before merging.
4. **Meeting minutes** go in `meetings/` within 24 hours of the meeting.
5. **Design decisions** are recorded in `decisions/` before they are presented to the supervisor or committee.

## Tagging a submission

When you submit a deliverable on Moodle, tag the same commit so you can prove exactly what was submitted and when:

```bash
git checkout main && git pull
git tag -a 494-abstract-v1.0 -m "Project abstract submitted on Moodle, YYYY-MM-DD"
git push origin 494-abstract-v1.0
```

Then create a GitHub Release from the tag and attach the submitted PDF. Resubmission after feedback: `v1.1`, `v1.2`, ...

## AI use

Follow the course AI policy: AI tools may help with grammar and clarity; disclose any substantive rephrasing; never use AI to generate content, citations, data or figures. Each pull request asks you to declare AI use.
