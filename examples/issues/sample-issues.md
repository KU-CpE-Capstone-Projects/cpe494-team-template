# Sample issues (fictional example)

Copy the *style*, not the content. Each issue has one owner, a due date, a milestone and acceptance criteria someone else can check.

---

### #18 · Task · Launch requirements survey
**Labels:** task, 494 · **Milestone:** 4 Requirements chapter · **Brief:** B4 · **Owner:** @hamad-example · **Due:** 2026-10-12

**What needs to be done**
Publish the piloted survey (v1.1) on Microsoft Forms and share via the department mailing list and library QR posters.

**Acceptance criteria**
- [ ] Consent text and 18+ screener included (template sections C and D)
- [ ] Every question appears in the traceability table
- [ ] ≥ 60 responses by the close date, or a note explaining the shortfall
- [ ] Export (no names or emails) saved to `research/results/survey-2026-10.csv`

---

### #22 · User story · See free seats before leaving home
**Labels:** requirement · **ID:** FR-04

As a **student**, I want to **see the number of free seats per library zone on my phone** so that **I can choose where to go before I walk over**.

**Acceptance criteria**
- [ ] Map shows each zone with free / total seats
- [ ] Data is no older than 60 s (NFR-03), and the page shows "updated N s ago"
- [ ] Works on a 360 px wide phone screen

**Source:** interviews P1, P3, P5; survey Q4 (mean usefulness 4.4)

---

### #31 · Bug · Node reports "occupied" after the chair is empty
**Labels:** bug · **Found in:** `494-poc-spec-v1.0` firmware

**Steps to reproduce**
1. Sit on the chair for 1 min, then stand and leave.
2. Watch the gateway log for 10 min.

**Expected:** state changes to free within 2 min. **Actual:** stays occupied for 30 min.
**Notes:** pressure pad reading drifts above threshold after release. Suspect threshold set too low; see DR-01 limitation.
