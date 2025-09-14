# AI-Ready Project Starter

A minimal, opinionated repo you can clone to kick off new projects **with an AI coding assistant in mind**.
Every session starts clean, pulls the right context, scopes a tiny task, ships it, and loops.

> If you’re here to just start building: jump to **Quick Start**.

---

## Why this template?

* **Self-hosting context.** The repo carries its own instructions so AI assistants don’t need prior memory.
* **Small, shippable tasks.** Guardrails enforce ≤3 files, ≤150 LOC, ≤90 minutes by default.
* **Repeatable loop.** One workflow file that every session follows.
* **Clear templates.** Canonical task/feature templates + instance folders.
* **Human-friendly.** Works great for humans without any AI tooling.

---

## Project Layout

```
.ai/
  assistant.md              # persistent rules for any AI assistant
  workflow.md               # single-session loop (start here every time)
  project-meta.yaml         # "contract": commands, constraints, conventions
  templates/
    task.md                 # DO NOT EDIT — template for tasks
    feature.md              # DO NOT EDIT — template for features
    session-start.md        # optional bootstrap text for new sessions
  context/
    current-task.md         # pointer to active task instance
    current-feature.md      # pointer to active feature instance
    architecture.md         # system decisions
    tech-stack.md           # tools/dependencies
  tasks/
    TASK-YYYYMMDD-001.md    # task instances (generated from templates)
    ...
  features/
    FEAT-123/
      feature.md            # feature instance (from template)
prd/
  mvp.md                    # current sprint goals
  backlog.md                # future features / tasks
  completed.md              # delivered features / tasks
src/
README.md
```

---

## Quick Start

1. **Clone & rename**

```bash
git clone <this-repo-url> my-new-project
cd my-new-project
```

2. **Set up the contract**: edit `.ai/project-meta.yaml`

* Fill repo URL, package manager, and the build/test/lint/run commands.
* Adjust task constraints if needed (defaults are good for most teams).

3. **Describe your stack**

* Add/update `.ai/context/architecture.md` and `.ai/context/tech-stack.md`.

4. **Create your first feature**

* Copy `.ai/templates/feature.md` → `.ai/features/FEAT-001/feature.md`
* Fill sections, especially **Problem**, **Acceptance Criteria**, and **Metrics**.
* Point `.ai/context/current-feature.md` to the new file:

  ```
  Active feature → ../features/FEAT-001/feature.md
  ```

5. **Create your first task**

* Copy `.ai/templates/task.md` → `.ai/tasks/TASK-YYYYMMDD-001.md`
* Fill all frontmatter and sections.
* Point `.ai/context/current-task.md` to it:

  ```
  Active task → ../tasks/TASK-YYYYMMDD-001.md
  ```

6. **Start a session**

* Open `.ai/templates/session-start.md` and paste its contents into your coding assistant.
* Follow the loop in `.ai/workflow.md`.

> Optional: add tiny scripts later (e.g., `scripts/new-task`, `scripts/new-feature`) to automate copying templates and updating pointers.

---

## The Single-Session Loop (how to work here)

**Always start at** `.ai/workflow.md`. Each session:

1. **Handshake** — read the contract + current feature/task + architecture/stack.
2. **Definition of Ready** — ensure task is tiny and testable.
3. **Plan** — list steps, file impacts, and test plan.
4. **Implement** — produce minimal diffs.
5. **Validate** — run tests/linters; do a self-review.
6. **Package** — share diff, commit message, and PR body.
7. **Close the loop** — mark the task done, update `prd/completed.md`, spin off a follow-up task if needed.

This keeps work small and momentum high.

---

## Templates, Instances, and Pointers

* **Templates** live in `.ai/templates/` and are **immutable**.
  Only change them in a dedicated “Template Update” PR.
* **Instances** live in `.ai/tasks/` and `.ai/features/` and are copies of templates you fill out.
* **Pointers** in `.ai/context/` are tiny files that point to “what’s active right now.”
  Change the pointer instead of overwriting a task/feature.

**Why?** A new AI session (or a new teammate) can instantly find the active work without reading a backlog.

---

## The Contract: `.ai/project-meta.yaml`

This is the machine-readable **source of truth** for:

* **Commands** to build, test, lint, format, and run the project.
* **Conventions** for commit style, branch naming, test globs, and coverage.
* **Constraints** that enforce small, shippable tasks (files/LOC/time caps).
* **Environments** and URLs for local/staging/prod.
* **CI hints** and default reviewer checklist.

**When to update it**

* When commands/conventions/constraints actually change (event-driven).
* After adding a new environment or changing URLs.
* When the team raises/lowers LOC/file caps or coverage thresholds.

**How to keep it healthy**

* Add `meta_version` and a tiny `changelog` inside the file.
* Never store secrets; point to `.env.example` or a secret manager.
* Include a PR checklist item: “If commands/conventions changed, update `project-meta.yaml`.”

---

## Creating Work

### New Feature

1. Copy template:

```
cp .ai/templates/feature.md .ai/features/FEAT-<ID>/feature.md
```

2. Fill **Problem**, **User Stories**, **Scope**, **Acceptance Criteria**, **Metrics**.
3. Create initial child tasks in `.ai/tasks/` and link them under **Child Tasks**.
4. Point `.ai/context/current-feature.md` to the new feature.

### New Task

1. Copy template:

```
cp .ai/templates/task.md .ai/tasks/TASK-<YYYYMMDD>-<slug>.md
```

2. Fill frontmatter and all sections.
3. Ensure **DoR** passes: single feature, ≤90min, ≤3 files, ≤150 LOC, rollback = revert one commit.
4. Point `.ai/context/current-task.md` to this task.

> Keep tasks tiny. If it’s getting big, split it and keep only the first slice active.

---

## Conventions

* **Commits**: Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, etc.).
* **Branches**: See `branching.pattern` in `project-meta.yaml`, e.g.
  `feat/FEAT-123-TASK-20250914-retry-widgets`
* **Tests**: Put tests next to code; match `test_match` globs in `project-meta.yaml`.
* **Style**: Project uses Prettier/ESLint (or your chosen tools in `project-meta.yaml`).
* **Security**: No secrets in code; use `.env.example` and a secret manager.

---

## First PR Checklist

* [ ] `project-meta.yaml` filled and accurate
* [ ] `architecture.md` and `tech-stack.md` sketched
* [ ] One feature instantiated + linked as current
* [ ] One small task instantiated + linked as current
* [ ] `README.md` updated with any team specifics (if needed)

---

## FAQs

**Q: Do I need an AI assistant to use this?**
No. The structure is helpful for humans too—small tasks, clear plans, good diffs.

**Q: Which files should I avoid editing?**
Everything in `.ai/templates/` (immutable templates) and the **pointers** should only change their target, not their content pattern.

**Q: What if I need a big refactor?**
Open a feature, write a short RFC in `features/FEAT-xxx/notes.md`, then split the refactor into tiny tasks that keep a green build between steps.

**Q: Where do I put credentials?**
Nowhere in the repo. Add placeholders to `.env.example` and read them at runtime.

---

## Optional: Scripts

You can add helper scripts later:

* `scripts/new-feature` → copies template, creates ID, updates pointer.
* `scripts/new-task` → copies template, timestamps ID, updates pointer, appends to `prd/backlog.md`.

These are not required to start; manual copying works fine.

---

## Using this project
# Clone the repository
git clone --<repo-url>-- my-new-project

# Navigate into the cloned directory
cd my-new-project

# Remove the original remote connection
git remote remove origin

# Verify remotes are gone (should show nothing)
git remote -v
