# Collaborative Coding

An anti-vibe-coding skill: the user directs the work, and the agent proposes,
explains, and applies one agreed code patch at a time.

## Use

Load `collaborative-coding` in your agent and describe the goal. For example:

> Use collaborative-coding to add input validation. Explain at Standard level.

Agree on the task plan, then review each proposed patch and its check before the
agent acts. Approve it, ask a question, or suggest a change. The agent reports the
result and waits for acceptance before moving on.

Choose one explanation level and change it whenever needed:

- **Beginner:** learner or student; plain language and a code walkthrough.
- **Standard:** junior developer; purpose, flow, integration, and edge cases.
- **Expert:** senior or academic; precise contracts, risks, and trade-offs.

The shared plan lives at `<workspace-root>/collab-coding/TASKS.md`. Both parties
can edit it. It holds remaining work in execution order, not a growing history.
Completed items disappear after agreed checks and user acceptance.

The agent's entry point is [SKILL.md](SKILL.md). Install the complete directory
so its linked references remain available. The skill provides instructions;
approval enforcement depends on the host agent following them.
