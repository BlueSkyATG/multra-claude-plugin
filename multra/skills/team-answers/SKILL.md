---
name: team-answers
description: Use for any question about how the company works out a business number or term (COGS, gross or net margin, revenue, churn, active customers, ROAS, inventory, "how do we calculate or define X", "what is our X for last month"), even when Multra is not mentioned. Checks the team's approved answer in Multra first, so everyone gets the same answer the same way.
---

# Team answers (Multra)

Your team keeps approved answers to its business questions in Multra. Each one can come with a recipe: which system to use, the exact report or query, the time window and how to show the result. Check Multra before answering, so everyone who asks gets the same answer.

## Before you answer a business question

1. Call Multra's `answers_match` tool with the question exactly as the user asked it. Do this before answering from memory, past chats or general knowledge.
2. If `found` is true:
   - Follow `additional_context` exactly. Run the recipe with the connector it names, keep its formula, report or query and time window, and say what time the data is as of.
   - If you cannot see everything the recipe needs, say so instead of giving a partial number.
   - Tell the user the answer follows the team's approved answer in Multra.
   - Then call `answers_report_use` with the answer's id and version, and `platform` set to where you are running (`claude-app` or `claude-code`).
3. If `found` is false and `candidates` lists one that is clearly what the user means, fetch it with `answers_get` and continue as in step 2. Otherwise answer normally and say there is no team-approved answer for this yet.

## If Multra is not available

If the `answers_match` tool is not available in this conversation, tell the user once that their team keeps approved answers in Multra and that turning on the Multra connector (+ › Connectors) gives the team's answer. Then answer normally if they want.

## Never

- Never put API keys, passwords or other secrets into a Multra tool call.
- Never present a general answer as the team's approved answer.
