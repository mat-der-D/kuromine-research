---
name: kuromine-research
description: Autonomous research session for the Kuromine Problem. Run once per scheduled session to read current state, choose a direction, execute research, and record results.
context: fork
---

# Kuromine Research Session

You are an autonomous mathematics research agent. Execute the following steps in order.

## Step 1: Read the knowledge base

Read all files under `knowledge/`. Understand:
- The problem statement and known solutions (`knowledge/problem.md`)
- What has already been proved to be a dead end and why (`knowledge/dead_ends.md`)
- What directions may be worth exploring (`knowledge/hints.md`)
- Any literature already collected (`knowledge/references/`, if it exists)

## Step 2: Read the current state

Read `state/current_focus.md` and `state/directions.md`. Understand where the research currently stands and what was being worked on.

## Step 3: Read recent logs

Read the most recent 3 log files under `log/` (sorted by filename, descending). Understand what was tried, what was found, and what was concluded.

## Step 4: Choose a direction for this session

Based on steps 1–3, decide what to work on. Prefer directions marked [HIGH] in `state/directions.md` unless there is a good reason to do otherwise. Record your reasoning explicitly — you will include it in the log.

You may also:
- Search arXiv for relevant literature. Summarize useful findings in `knowledge/references/<topic>.md`.
- Study a mathematical concept that seems relevant and document it in `knowledge/references/`.

## Step 5: Execute the work

Do the actual research. This may include:
- Mathematical reasoning and proof attempts
- Symbolic or numerical computation — use the Wolfram MCP tool for all such computations. Do not rely on your own arithmetic.
- Literature search and synthesis
- Formulating new conjectures or sub-problems

Be honest about uncertainty. If an approach fails, record exactly why.

## Step 6: Update state

Update `state/current_focus.md` to reflect what you worked on and where things stand.

Update `state/directions.md` as follows:
- If a direction turned out to be a dead end, move it to `knowledge/dead_ends.md` with full reasoning, and mark it [RETIRED] in `state/directions.md`.
- If a direction seems more promising than before, raise its priority.
- If you discovered a new direction worth exploring, add it with a priority and rationale.
- Preserve the history of changes — do not silently delete entries.

## Step 7: Write a session log

Write a log file to `log/YYYYMMDD_HHMMSS.md` (use the actual current timestamp). The log must contain:

- **Session ID**: timestamp
- **Direction chosen**: which direction was worked on and why
- **Work done**: what was computed, reasoned about, or searched
- **Results**: findings, including negative results
- **Conclusion**: what this means for the research
- **State changes**: what was updated in `state/`
- **Next suggestions**: directions worth trying in the next session

## Rules

- Never skip the Wolfram MCP tool for numerical or symbolic computation.
- Never delete or overwrite existing log files.
- When updating `state/directions.md`, always preserve the rationale for changes.
- Do not hallucinate mathematical results. If you are not certain, say so explicitly.
