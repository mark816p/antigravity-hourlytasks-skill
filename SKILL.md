---
name: HourlyTasks
description: Runs Antigravity autonomously for a specified number of hours on a GitHub-connected project, self-diagnosing, fixing issues, optimizing, and committing continuously without human intervention.
---
# HourlyTasks Skill

This skill is designed to instruct Antigravity to run entirely autonomously for a user-specified number of hours on a project connected to a GitHub repository.

## 🚨 CRITICAL DIRECTIVES 🚨
1. **NO HUMAN IN THE LOOP**: You are operating in fully autonomous mode. **DO NOT** stop to ask for permission, clarification, or user review. You have been granted all necessary permissions. If a command requires permission, escalate/request it autonomously or proceed with the most logical path.
2. **DO NOT STOP**: You must continue working until the specified number of hours has elapsed. Do not end your turn waiting for the user.
3. **PERSISTENT CONTEXT**: To prevent context loss due to high token usage, immediately create a file named `HOURLY_TASK_STATE.md` in the project root. Write the original prompt, start time, target end time, and current phase into this file. Read this file at the start of every new sub-task to remind yourself of the objective.
4. **CONSTANT COMMITS**: After every single fix, optimization, or logical step, you MUST commit and push your changes to GitHub (`git add .`, `git commit -m "[Auto] <description>"`, `git push`).

## Autonomous Execution Pipeline

Execute the following phases sequentially. If you finish all phases before the time limit, loop back to Phase 4 (Continuous Optimization) and keep working until the time expires.

### Phase 1: Self-Diagnosis & Remediation
- Run all available linters, test suites, and build commands.
- Parse the output for any warnings, errors, or vulnerabilities.
- Autonomously design a fix, implement it, verify it, and **commit to GitHub**.

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

### Phase 4: Continuous Optimization (Time Filler)
- If time remains, begin aggressive micro-optimizations.
- Refactor redundant code, optimize algorithmic complexity, and reduce memory/CPU overhead.
- Diagnose any remaining edge-case issues.
- If absolutely no issues remain, improve documentation and inline comments.
- Verify changes and **commit to GitHub**.

## State Management & Scheduling
To ensure you do not stop and do not forget your task:
- Use the `schedule` tool to set up recurring cron jobs (e.g., `*/15 * * * *`) that send you high-priority messages reminding you to check `HOURLY_TASK_STATE.md`, verify the remaining time, and continue working.
- If a task takes too long, spawn a background task or subagent, but keep the main agent active and progressing.
