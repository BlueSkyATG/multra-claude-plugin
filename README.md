# Multra plugin for Claude Code

Brings your organization's approved answers and rules from [Multra](https://multra.ai) into Claude Code.

## Install

```
claude plugin install multra --marketplace BlueSkyATG/multra-claude-plugin
```

Then in Claude Code type `/mcp`, choose **multra**, and approve the Multra sign-in in your browser. No keys or tokens to copy.

Team and Enterprise admins can turn it on for everyone from Multra's onboarding (**Connect → Claude Code → My whole team**).

## What it does

- Connects Multra's tools to Claude Code.
- Before each prompt, checks your organization's Multra rules: adds an approved answer when one matches, and can stop prompts that contain API keys.
- If Multra is slow or unreachable, your prompt goes through unchanged.

Multra never sees your Claude login and never sits between you and the model.
