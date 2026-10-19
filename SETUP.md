# Setup guide

## For the instructor (once per offering)

1. Create a GitHub organization or use the department one (e.g. `ku-cpe-capstone-2026`).
2. Push this repository to it and open **Settings → General → Template repository** (tick it).
3. Decide who creates team repos:
   - **Self-serve:** allow members to create private repositories; each team clicks **Use this template**.
   - **Instructor-controlled:** you create `TeamName-2026` from the template and add the team.
4. Add yourself and the TA/engineer to every team repo with **Write** (or **Maintain**) access.

## For each team (week 1)

1. **Use this template → Create a new repository**: name it `<teamname>-cpe494-2026`, visibility **Private**.
2. **Settings → Collaborators:** add every teammate (Write) and the supervisor and TA.
3. **Settings → Branches → Add branch protection rule** for `main`:
   - Require a pull request before merging
   - Require approvals: **1**
   - Require status checks: **Repo check / structure**
   Without this rule anyone can merge unreviewed work, and your review history will not count as evidence.
4. **Issues → Labels:** keep `task`, `requirement`, `bug`; add `blocked`, `494`, `495`.
   If the labels are missing, open Actions → "Set up labels" → Run workflow.
5. **Set up the project board** and **link GitHub to your Teams channel**: follow the two sections below.
6. **First pull request (everyone reviews):** fill in `README.md` (team table, links) and `TEAM_AGREEMENT.md`. Every member approves it; that approval is your signature on the team agreement.
7. Add the team-formation documents to `docs/494/01-team-formation/`, submit on Moodle, and tag `494-team-formation-v1.0`.
8. When a brief (B1–B16) is posted in the class team, open one Task issue per piece of work and pick that brief in the form.

## Project board (GitHub Projects)

The board is the team's **single task list**. Every piece of work is an issue on it; nothing is tracked only in WhatsApp or in meeting minutes. The supervisor opens it before every meeting.

### 1. Create the board (team leader, 10 minutes)

1. On the repository page: **Projects → Link a project → New project → Board**. Name it `<teamname> CpE-494/495`.
2. Open the project's **⋯ → Settings → Manage access** and give every teammate **Write** and the supervisor and TA at least **Read**.

### 2. Columns (the Status field)

Edit the **Status** field so it has exactly these options, in this order:

| Column | Means |
| --- | --- |
| To do | Agreed and assigned, not started |
| In progress | Someone is working on it now |
| In review | A pull request is open and waiting for a teammate's review |
| Done | Merged or accepted; acceptance criteria met |

Blocked work stays in its column and gets the `blocked` label, with a comment saying what is needed (see the blocker format in the Decision Record template).

### 3. Fields

1. **Milestone:** in the repository, **Issues → Milestones → New milestone**, one per row of the README deliverables table, with its due date. Then show the **Milestone** field on the board.
2. **Week:** in the project, **+ → New field → Iteration**, name it `Week`, duration **1 week**, starting on week 1 of the semester.
3. Add these custom fields with **+ → New field**:

   | Field | Type | Options | Used for |
   | --- | --- | --- | --- |
   | Brief | Single select | None, B1 … B16 | Which task post the work answers. Pick the same value as in the issue form. |
   | Size | Single select | S (≤ 2 h), M (half day), L (≥ 1 day) | Spotting tasks that are too big; split anything larger than L |

### 4. Automations

In the project, open **⋯ → Workflows** and switch on:

- **Auto-add to project:** filter `is:issue,pr is:open` for this repository, so every new issue appears on the board.
- **Item closed → Done** and **Pull request merged → Done**.
- **Item reopened → In progress**.

### 5. Saved views

| View | Layout | Filter / grouping | Used in |
| --- | --- | --- | --- |
| Board | Board | All open items | Day to day |
| This week | Board | `iteration:@current` | Weekly team meeting |
| By person | Table | Group by **Assignees**, sort by Status | Supervisor progress checks |
| By milestone | Table | Group by **Milestone** | Before each submission |

### 6. Rules the team agrees to

- No work without an issue on the board, with **one assignee**, a due date and a milestone.
- Move your own cards the same day the status changes.
- In the weekly meeting, go through the **This week** view; the minutes link issue numbers instead of re-typing a task table.
- An item in **In progress** for more than a week is either split or marked `blocked`.

### What the supervisor looks at

Before each meeting: items in **In progress** older than a week, anything labeled `blocked`, and the **By person** view. These are the agenda. The board is evidence for the commitment and teamwork grades; the board itself is not graded.

## Link GitHub to your Teams channel

So that issues, pull requests and reviews appear in the team's Microsoft Teams channel, next to supervisor feedback.

1. In Microsoft Teams, open your group's team, then **Apps** (left bar) and search for **GitHub**. Add it to the team's channel.
2. In that channel, type `@GitHub signin` and sign in with your GitHub account.
3. Subscribe the channel to the repository:

   ```
   @GitHub subscribe <owner>/<repo> issues pulls reviews releases
   ```

   Check the subscription with `@GitHub subscribe list`. To reduce noise, remove a feature with `@GitHub unsubscribe <owner>/<repo> <feature>`.
4. Post a test: open an issue and confirm it appears in the channel.

If the GitHub app is not available in your Teams (the university may restrict third-party apps), ask the department IT office to enable it. Until then, post the board link in the channel's **+ (tab)** bar as a **Website** tab so everyone can open the board from Teams.

Use Teams for discussion and supervisor communication, and the board for tasks. Do not add a third chat tool for project work.
