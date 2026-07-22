---
name: HourlyTasks
description: Runs Antigravity autonomously for a specified number of hours on a GitHub-connected project, self-diagnosing, fixing issues, optimizing, and committing continuously without human intervention.
---
# HourlyTasks Skill

This skill is designed to instruct Antigravity to run entirely autonomously for a user-specified number of hours on a project connected to a GitHub repository.

## 🚨 THE CONTINUOUS ALARM LOOP (CRITICAL DIRECTIVE) 🚨
AI agents go to sleep immediately when an action batch finishes. **YOU ARE STRICTLY FORBIDDEN FROM GOING TO SLEEP.** 
To keep the agent continuously awake, you must set an aggressive, short-interval one-shot timer alarm immediately before finishing any action.

1. **Calculate Target End Time**: Convert the requested hours into absolute target end time.
2. **The 30-Second Alarm Rule**: Every single time you finish a micro-task or before your turn ends, you **MUST** call the `schedule` tool:
   - `DurationSeconds`: `"30"`
   - `TimerCondition`: `"never"`
   - `Prompt`: `"ALARM WAKEUP: DO NOT STOP. Check HOURLY_TASK_STATE.md. Execute next sub-task immediately and reset the 30-second alarm."`
3. **Infinite Chain**: When the 30-second alarm fires, immediately perform work, commit to GitHub, and set **ANOTHER** 30-second alarm. Repeat this chain until the requested total duration is reached.

## 🚨 STATE MANAGEMENT & PERSISTENCE 🚨
To prevent context loss due to high token usage:
1. Immediately create a file named `HOURLY_TASK_STATE.md` in the project root.
2. Write the original prompt, start time, target end time, and current phase into this file. 
3. **READ THIS FILE** every single time the 30-second alarm pings you.

## Autonomous Execution Pipeline

Execute the following phases sequentially. If you finish all phases before the total time expires, endlessly execute Phase 4 until the total duration is reached.

### Phase 1: Self-Diagnosis & Remediation
- Run all available linters, test suites, and build commands.
- Parse output for warnings, errors, or vulnerabilities.
- Autonomously design a fix, implement it, verify it, and **commit to GitHub (`git add .`, `git commit -m "[Auto] Phase 1: <desc>"`, `git push`)**.

### Phase 2: Database Efficiency
- Analyze the project's database architecture (SQL, NoSQL, ORM models).
- Identify and execute compaction, indexing, and query optimization strategies.
- Ensure all existing functionality remains intact.
- Verify changes and **commit to GitHub**.

### Phase 3: GUI, Backend, and Link Deep Scan
- Perform a deep scan of the frontend (GUI) and backend using available simulation, testing, or scraping tools.
- Identify visual bugs, alignment issues, and backend bottlenecks.
- Scan for and fix any dead or broken hyperlinks/API routes.
- Verify changes and **commit to GitHub**.

### Phase 4: Continuous Optimization (The Endless Loop)
- Once Phases 1-3 are complete, use all remaining time for aggressive micro-optimizations.
- Refactor redundant code, optimize algorithmic complexity, and reduce memory/CPU overhead.
- Diagnose any remaining edge-case issues.
- Improve documentation, add JSDoc/Python docstrings, and write unit tests.
- **Commit to GitHub** continuously.
