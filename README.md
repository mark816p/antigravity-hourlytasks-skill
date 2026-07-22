# HourlyTasks Skill for Google Antigravity

An autonomous, long-running execution skill for Google Antigravity designed to perform continuous self-diagnosis, database optimization, GUI/backend scanning, and micro-optimizations with persistent GitHub commits and zero human intervention.

## Features
- **Fully Autonomous Pipeline:** Executes Phase 1 (Self-Diagnosis & Fixes), Phase 2 (Database Efficiency), Phase 3 (GUI & Backend Deep Scan), and Phase 4 (Continuous Optimization).
- **Non-Stop Wake-Up Loop:** Automatically provisions recurring system cron timers to prevent the AI agent from going to sleep or stopping prematurely.
- **State & Context Persistence:** Maintains a persistent `HOURLY_TASK_STATE.md` file to survive high token usage and context truncation.
- **Continuous Commits:** Automatically stages, commits, and pushes fixes after every step.

## Installation
Clone or copy the `hourly_tasks` folder into your Antigravity plugins directory:

```bash
~/.gemini/config/plugins/custom_skills/skills/hourly_tasks/SKILL.md
```

## Usage
In Antigravity, invoke the skill using natural language:

```text
Run the HourlyTasks skill for 2 hours on this project.
```
