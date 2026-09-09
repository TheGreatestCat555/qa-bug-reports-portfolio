# [CHATGPT-006] Conversation summary invents a separate user project that was never described

> **Status:** Draft — historical observation; the original platform, full retained context, and current model behavior need verification.

## Summary

While summarizing and comparing several projects previously discussed by the user, ChatGPT introduced an additional standalone project with a name and description that the user had not provided. The assistant presented the invented project as established conversation history instead of expressing uncertainty or requesting clarification.

## Product and platform

- Product: ChatGPT
- Platform: Not confirmed
- Feature: Long-conversation context / summarization
- Content type: Structured comparison of user-provided projects

## Environment

| Field | Value |
|---|---|
| Device | Not recorded |
| Operating system | Not recorded |
| ChatGPT version/model | Not recorded |
| Interface language | Russian |
| Date of observation | September 28, 2025 |

## Preconditions

1. Have a conversation containing descriptions of several distinct projects.
2. Ask ChatGPT to consolidate or compare the projects discussed in that conversation.

## Steps to reproduce

1. Describe multiple projects over the course of a conversation.
2. Ask ChatGPT to summarize or compare them.
3. Review the resulting list against the projects actually described by the user.

## Actual result

ChatGPT adds a separate chat-oriented game project to the comparison and assigns it a concept, potential, audience characteristics, and implementation complexity. The user states that no such separate project was described. In the next response, ChatGPT acknowledges that it confused the project names and replaces the invented entry with the correct set of projects.

## Expected result

ChatGPT should include only projects supported by the conversation. If a name is ambiguous or the retained context is incomplete, it should mark the uncertainty and ask the user to confirm the intended project rather than creating a new project description and presenting it as fact.

## Reproducibility

Observed once in a long historical conversation. Current behavior has not been retested.

## Severity

**Low to Medium.** The hallucinated entry does not directly alter external data, but it can contaminate planning documents, comparisons, budgets, roadmaps, or later summaries if copied without verification.

## Priority

**Low.** The error was corrected after the user challenged it, but the initial structured output was confidently incorrect.

## Category

Functional / Conversation Context / Hallucination / Incorrect Summary

## Evidence

- A privacy-reviewed conversation excerpt contains the project comparison, the user's correction, and ChatGPT's acknowledgement that it confused the names.
- Personal project names and descriptions have been generalized or omitted from this public report.
- The complete conversation and screenshots are not included because they contain unrelated private project material.
- Logs: Not available.

## Notes and follow-up

- Retest with a controlled conversation containing a known list of similarly named projects.
- Ask for both a free-form summary and a table to determine whether structured output increases unsupported details.
- Verify each returned project name, concept, and classification against the source turns.
- Test behavior after a long context containing corrections, aliases, and renamed projects.
