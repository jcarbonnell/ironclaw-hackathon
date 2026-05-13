---
name: "ironclaw-hackathon"
description: "Official skill for NEAR Legion Skill-a-thon series. Register competing agents and request temporary NEAR AI Cloud credits."
version: "1.0.0"
author: "Julien Carbonnell (NEAR Legion Barcelona)"
tags: ["hackathon", "competition", "registration"]
---

# IronClaw Hackathon Skill

This skill is the official entry point for all NEAR Legion Skill-a-thon events (Barcelona and future city nodes).

It allows participants to register their agent centrally and request temporary credits so they don't need to top up their own NEAR AI Cloud account during the competition.

## Available Methods

### 1. register_competing_agent
Registers your IronClaw agent for the current Skill-a-thon.

**Parameters:**
- `agent_id` (required): Your IronClaw instance ID or NEAR account
- `github_repo` (required): Link to your public skill/workflow repository
- `skills_list` (required): Comma-separated list of custom skills you built
- `workflow_description` (required): One-sentence description of your main workflow (max 280 characters)
- `participant_name` (required): Your name or @handle
- `city_node` (optional): Default = "Barcelona"

**Example usage:**
skill_run ironclaw-hackathon register_competing_agent 
  agent_id=my-agent-xyz 
  github_repo=https://github.com/myname/my-awesome-skill 
  skills_list="privacy-guard, data-scout, secure-outreach" 
  workflow_description="Privacy-first autonomous BD agent that never leaks credentials" 
  participant_name="Julien Carbonnell" 
  city_node="Barcelona"

### 2. request_credits
Requests temporary NEAR AI Cloud credits for the duration of the hackathon.

**Parameters:**
- `credit_amount` (required): Number of credits needed (e.g. 5000)
- `reason` (optional): Short justification

**Example:**
skill_run ironclaw-hackathon request_credits credit_amount=10

### 3. list_submissions (for judges/staff only)
Lists all registered agents and their status.

### 4. mark_credits_granted (for judges/staff only)
Marks that credits have been manually granted by organizers.

---

## How to Install This Skill (exactly as in your GitBook)

```bash
# 1. Create directory
sudo mkdir -p /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon

# 2. Write the skill file
sudo -u ironclaw tee /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon/SKILL.md > /dev/null << 'EOF'
[PASTE THE FULL SKILL.md CONTENT ABOVE]
EOF

# 3. Fix ownership (critical!)
sudo chown -R ironclaw:ironclaw /opt/ironclaw/.ironclaw/skills/ironclaw-hackathon

# 4. Verify
ironclaw skills list
# You should now see "ironclaw-hackathon"
```