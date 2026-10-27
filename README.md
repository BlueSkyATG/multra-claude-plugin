# Multra plugin for Claude

Brings your organization's approved answers and rules from [Multra](https://multra.ai) into the Claude app and Claude Code.

## Claude app (Team and Enterprise)

An owner adds it once for everyone:

1. **Organization settings › Connectors**: add Multra (`https://multra.ai/api/mcp`). Each person connects it once with their own Multra sign-in.
2. **Organization settings › Plugins & skills**: add this plugin from GitHub (`BlueSkyATG/multra-claude-plugin`) and set it to **Required**.
3. **Organization settings › Code execution and file creation** and **Skills** must be on: skills need them.

Multra's setup page has these steps with copy buttons, and an optional one-line organization instruction.

## Claude Code

```
claude plugin install multra --marketplace BlueSkyATG/multra-claude-plugin
```

Then type `/mcp`, choose **multra**, and approve the Multra sign-in in your browser. No keys or tokens to copy. Team and Enterprise admins can turn it on for everyone from Multra's onboarding (**Connect → Claude Code → My whole team**).

## What it does

- **Team answers skill:** for any question about how the company works out a business number (COGS, margin, churn…), Claude checks the team's approved answer in Multra first, follows its recipe, and says it is the team's answer.
- **Claude Code prompt check:** before each prompt, checks your organization's Multra rules: adds an approved answer when one matches, and can stop prompts that contain API keys. If Multra is slow or unreachable, the prompt goes through unchanged.
- Connects Multra's tools.

Multra never sees your Claude login and never sits between you and the model.
