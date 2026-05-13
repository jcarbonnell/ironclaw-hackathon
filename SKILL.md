---
name: "ironclaw-hackathon"
description: "Official skill for NEAR Legion Skill-a-thon series. Register your agent and request temporary NEAR AI Cloud credits."
version: "0.1.0"
author: "Julien Carbonnell (NEAR Legion Barcelona)"
tags: ["hackathon", "competition", "registration", "credits"]
---

# ironclaw-hackathon

Official skill for the NEAR Legion Skill-a-thon series (Barcelona and all future city nodes).

It allows participants to register their IronClaw agent centrally and request temporary NEAR AI Cloud credits without needing to top up their own account.

## Available Methods

### 1. register_competing_agent
Register your agent for the current Skill-a-thon.

**Parameters:**
- `agent_id` (required) — your IronClaw agent ID or NEAR account
- `github_repo` (required) — link to your public skills/workflows repo
- `skills_list` (required) — comma-separated list of custom skills you built
- `workflow_description` (required) — one-sentence description of your main workflow
- `participant_name` (required) — your name or @handle
- `city_node` (optional, default: "Barcelona")

**What the skill does:**
1. Reads the current submissions file for this event.
2. Appends a clean, readable entry using `memory_write`.
3. Confirms registration to you.

### 2. request_credits
Request temporary NEAR AI Cloud credits for the hackathon duration.

**Parameters:**
- `credit_amount` (required) — e.g. 5000 or 8000
- `reason` (optional)

**What the skill does:**
1. Logs your credit request to the shared submissions file.
2. Notifies organizers/judges automatically.

### 3. list_submissions (for judges & staff)
Display all registered agents and credit requests for the current event.

**What the skill does:**
- Uses `memory_read` to show the full, up-to-date submissions markdown file.

---

## Installation (one-time, same as in the GitBook)

```bash
# 1. Create the skill directory
sudo mkdir -p /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon

# 2. Write the skill file
sudo -u ironclaw tee /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon/SKILL.md > /dev/null << 'EOF'
[PASTE THE ENTIRE CONTENT ABOVE HERE]
EOF

# 3. Fix ownership (very important!)
sudo chown -R ironclaw:ironclaw /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon

# 4. Verify
ironclaw skills list
# You should now see "ironclaw-hackathon"
```