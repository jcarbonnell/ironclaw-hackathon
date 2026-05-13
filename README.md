# ironclaw-hackathon

**Official skill for the NEAR Legion Skill-a-thons**

Used by participants to submit their IronClaw agent and request temporary NEAR AI Cloud credits for the competition.

This is the first edition (Barcelona). The exact same format and skill can be cloned by every NEAR Legion City Node or IronClaw Hackathon organizers.

## How it works

### For participants
1. Deploy your own IronClaw node (Starter plan is free).
2. Build your privacy-first skills and workflows.
3. At submission time, run **one command** in your REPL:

```bash
skill_run ironclaw-hackathon register_competing_agent \
  agent_id=your-agent-id \
  github_repo=https://github.com/yourname/your-skill \
  skills_list="secure-memory, data-guard" \
  workflow_description="Privacy-first autonomous BD agent that never leaks credentials" \
  participant_name="Your Name"
```