# WORKFLOW.md — How this change was made

This repository exists so you can follow a real change through the full Git &amp; GitHub flow. Below is the exact sequence of steps that produced the README and this file. Follow along in the UI and you'll see every artifact of the flow.

## The story

| Step | Artifact | Where to find it |
|------|----------|------------------|
| 1. Describe the work | [Issue #1](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/issues/1) | Issues tab |
| 2. Create a branch | `add-profile-credits` | Branch dropdown on the code page |
| 3. Commit the README change | Commit `75014a5` | Branch → Commits |
| 4. Open a pull request | [Pull request #2](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/pull/2) | Pull requests tab |
| 5. Commit the guide (this file) | Commit on `add-profile-credits` | Branch → Commits |
| 6. Check status &amp; checks | PR #2's Checks and status | Pull request page |
| 7. Merge into `main` | Merge commit on `main` | `main` → Commits |
| 8. Close the issue | Issue #1 closes via `Closes #1` | Issues tab (closed) |

## Step-by-step guide

### 1. Write a short issue first
Before touching any code, open an issue that describes what you want to change and why. Here that's [issue #1](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/issues/1): *"Improve README with instructor profile credits and workshop context."* The issue is the unit of work everything else references.

### 2. Create a feature branch
Never commit straight to `main`. Create a short, descriptive branch for the work:

```
git switch -c add-profile-credits
```

A branch is where you can experiment safely; `main` stays clean until your change is reviewed.

### 3. Make small, focused commits
Split the work into commits that each do one thing. On this branch there are exactly two:

1. **`75014a5` — Update README.md** — adds the instructor's display name, bio, and profile link, plus workshop context. Commit message ends with `(refs #1)` to tie it to the issue without closing it early.
2. **This commit — Add WORKFLOW.md** — the guide you're reading now, which cites the real issue and pull request numbers.

Use commit messages in the imperative mood: "Add…", "Fix…", not "Added…" or "Fixes…".

### 4. Open a pull request
Push the branch and open a [pull request](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/pull/2) into the default branch (`main`). In the description:

- Say **what** the PR does and **why**, linking back to the issue.
- Include the phrase `Closes #1` so GitHub automatically closes issue #1 when the PR merges.

A good PR is small, has a clear description, and references its issue.

### 5. Watch the status checks
Before merging, look at what the PR's status and checks report. On PR #2 the commit status reported **success** and no failing CI checks were blocking the merge. If checks had failed, you'd push fixes to the same branch and the PR would update automatically — no new PR needed.

### 6. Merge
Once the checks pass and the PR is approved, merge it. GitHub then shows the pull request as **merged**, and the `main` branch contains your change.

### 7. The issue closes itself
Because the PR description contained `Closes #1`, merging automatically closed issue #1. Check the Issues tab: it should show no open issues.

## Things to try yourself

- Open `main` and read `README.md` — the credits you see there came through this flow.
- Look at [PR #2](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/pull/2)'s **Commits** tab to see the two commits.
- Look at [issue #1](https://github.com/mcpmark-eval-liuhezi/pr-workflow-demo/issues/1)'s timeline to see it referenced by the PR and closed on merge.
- Click the **Checks** tab on the PR to see what CI reported.
